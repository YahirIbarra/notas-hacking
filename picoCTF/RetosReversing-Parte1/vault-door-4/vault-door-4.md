## Objetivo
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java)

## Pistas
- Use a search engine to find an "ASCII table".
- You will also need to know the difference between octal, decimal, and hexadecimal numbers.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ ls
VaultDoor4.java
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ cat VaultDoor4.java 
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
            '4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ nano Password.java
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ nano Password.java 
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ cat Password.java  
import java.nio.charset.StandardCharsets;

public class Password {
        public static void main(String[] args){
                byte[] myBytes = {
                106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
                0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
                0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
                '4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
                };
                System.out.println(new String(myBytes, StandardCharsets.UTF_8));
        }
}
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ javac VaultDoor4.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ javac Password.java                           
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ java Password                                 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-4]
└─$ java VaultDoor4         
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}
Access granted.


Flag: picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}
```

## Notas adicionales


## Referencias

