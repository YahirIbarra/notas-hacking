## Objetivo
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/943ea40e3f54fca6d2145fa7aadc5e09/VaultDoor3.java)

## Pistas
- Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ ls
VaultDoor3.java
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ cat VaultDoor3.java 
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just *know* this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm18g947_u_4_m9r54f");
    }
}
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ nano Password.java
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ cat Password.java  
public class Password {
        public static void main(String[] args){
                String password = args[0];
                char[] buffer = new char[32];
                int i;
                for (i=0; i<8; i++) {
                        buffer[i] = password.charAt(i);
                }
                for (; i<16; i++) {
                        buffer[i] = password.charAt(23-i);
                }
                for (; i<32; i+=2) {
                        buffer[i] = password.charAt(46-i);
                }
                for (i=31; i>=17; i-=2) {
                        buffer[i] = password.charAt(i);
                }
                String s = new String(buffer);
                System.out.println(s);
        }
}
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ javac Password.java  
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ java Password jU5t_a_sna_3lpm18g947_u_4_m9r54f
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
jU5t_a_s1mpl3_an4gr4m_4_u_79958f
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ javac VaultDoor3.java                                                                                      1 ⨯
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/vault-door-3]
└─$ java VaultDoor3      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}
Access granted.



Flag: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}
```

## Notas adicionales


## Referencias

