# Password Cracking

## Abstract
Throughout the password cracking process, various tools and techniques were used on different virtual machines within the lab environment. This provided a practical understanding of how to crack hashed passwords from different systems. John the Ripper was used in single mode and Hashcat was used for dictionary and mask attacks to crack both Linux and Windows password hashes.

## Introduction
This report was developed using different tools and techniques to crack hashed passwords from two different hash files. The purpose of this exercise is to understand the importance of different password cracking methods and tools. Performing these tasks provided me with crucial information that can be used to understand the security posture of these systems.

## VM IPs
### Kali IP: 192.168.48.129

## Hash Files
### linpasshash
- ![image](https://github.com/user-attachments/assets/04ccc3ed-577d-4fdc-8970-3736928d30fe)


### winpasshash
- ![image](https://github.com/user-attachments/assets/feacd86e-cdbc-4c26-bdea-74a628c8ae4f)


## Single Mode Attacks

### Linux
Using John in single mode, we can attempt to crack the Linux hashes to find plain text passwords. 
- ![image](https://github.com/user-attachments/assets/7dcd3d47-48f2-485e-9640-0f6658b7b597)
   - This image shows the output of John the Ripper in single mode attempting to crack Linux password hashes.


john.pot contents:
- ![image](https://github.com/user-attachments/assets/b1d905bf-185d-4e6b-918b-0f133903793a)
   - THis image shows the contents of `john.pot` which contains all of the cracked passwords.


### Windows
Using John in single mode, we can attempt to crack the Windows hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/a9fc7c35-3130-44dd-b829-578f0c771d0a)
   - This image displays the output of John the Ripper in single mode attempting to crack Windows password hashes.


john.pot contents:
- ![image](https://github.com/user-attachments/assets/0cebfc49-d9f2-4f1f-979c-88c3a938327a)
   - This image shows the contents of `john.pot` which contains all of the cracked passwords.

     
## Dictionary Attacks

### Linux

- `-m 500`: Specifies the hash type. `500` is for SHA-1, which is commonly used for Linux password hashes.
- `-a 0`: Specifies the attack mode. `0` is for a dictionary attack.
- `-o cracked_linpasshash.txt`: Specifies the output file where cracked passwords will be saved.


Using Hashcat with the `rockyou.txt` wordlist, we can attempt to crack the Linux hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/a0af445d-fa17-4154-9987-40ff88ae7a88)
   - This image shows the Hashcat command using the rockyou.txt wordlist to crack Linux password hashes.


- ![image](https://github.com/user-attachments/assets/35a6e95a-d704-473e-a831-ce5e6d2f8838)
   - This image shows the cracked Linux passwords. 


### Windows

#### LM

- `-m 3000`: Specifies the hash type. `3000` is for LM (LAN Manager) hashes, which are also used in older Windows systems.
- `-a 0`: Specifies the attack mode. `0` is for a dictionary attack.
- `-o cracked_winpasshash_lm.txt`: Specifies the output file where cracked passwords will be saved.


Using Hashcat with the `rockyou.txt` wordlist, we can attempt to crack the Windows LM hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/84a9801a-3124-4d71-b13b-5199bda6b52a)
   - This image displays the output of Hashcat using a wordlist to crack Windows LM password hashes.


#### NTLM

- `-m 1000`: Specifies the hash type. `1000` is for NTLM, which is commonly used for Windows password hashes.
- `-a 0`: Specifies the attack mode. `0` is for a dictionary attack.
- `-o cracked_winpasshash.txt`: Specifies the output file where cracked passwords will be saved.


Using Hashcat with the `rockyou.txt` wordlist, we can attempt to crack the Windows NTLM hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/bf0e8304-af28-4d44-b97d-9445b93cffb7)
   - This image displays the output of Hashcat using a wordlist to crack Windows NTLM password hashes.


- ![image](https://github.com/user-attachments/assets/8ca20c92-0d15-4b61-a82c-c4ae1ea7547e)
   - This image shows the cracked NTLM hashed passwords. 

     
## Mask Attack Mode

### Linux

#### MD5

- `-m 500`: Specifies the hash type. `500` is for SHA-1.
- `-a 3`: Specifies the attack mode. `3` is for a mask attack.
- `-o cracked_linpasshash_mask.txt`: Specifies the output file where cracked passwords will be saved.
- `linpasshash`: The file containing the Linux password hashes to be cracked.
- `?a?a?a?a?a?a?a?a`: The mask pattern, where `?a` represents any character (letters, numbers, symbols).


Using Hashcat in mask attack mode, we can attempt to crack the Linux password hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/55e8e520-1d77-44db-99b0-557a7e266357)
- ![image](https://github.com/user-attachments/assets/34a16463-894b-4e7a-bd24-104e8353d6a4)
   - These images show the result of Hashcat command using a MD5 mask attack to crack Linux password hashes.


### Windows

#### NTLM

- `-m 1000`: Specifies the hash type. `1000` is for NTLM.
- `-a 3`: Specifies the attack mode. `3` is for a mask attack.
- `-o cracked_winpasshash_mask.txt`: Specifies the output file where cracked passwords will be saved.
- `winpasshash`: The file containing the Windows password hashes to be cracked.
- `?a?a?a?a?a?a?a?a`: The mask pattern, where `?a` represents any character (letters, numbers, symbols).


Using Hashcat in mask attack mode, we can attempt to crack the Windows NTLM password hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/b4f65934-1c97-46c8-b091-96db27d18507)
   - This image displays the output of Hashcat using a mask attack to crack Windows NTLM password hashes.
     
- ![image](https://github.com/user-attachments/assets/0a60c552-fdf5-4c90-8087-840676c9f705)
   - This image displays the output file with NTLM hash cracking in progress.

#### LM

- `-m 3000`: Specifies the hash type. `3000` is for LM (LAN Manager) hashes, which are also used in older Windows systems.
- `-a 3`: Specifies the attack mode. `3` is for a mask attack.
- `-o cracked_winpasshash_lm_mask.txt`: Specifies the output file where cracked passwords will be saved.
- `winpasshash`: The file containing the Windows password hashes to be cracked.
- `?a?a?a?a?a?a?a?a`: The mask pattern, where `?a` represents any character (letters, numbers, symbols).


Using Hashcat in mask attack mode, we can attempt to crack the Windows LM password hashes to find plain text passwords.
- ![image](https://github.com/user-attachments/assets/1101b5c3-07f4-42a4-8f5f-f8f5d363a236)
   - This image displays the output of Hashcat using a mask attack to crack Windows LM password hashes.
     
- ![image](https://github.com/user-attachments/assets/e7dfdd50-a613-4dd8-81b0-c880c110131d)
   - This image displays the output file with LM hash cracking in progress. 


## Methodology
This project demonstrated the effectiveness of various password cracking tools and techniques, such as John the Ripper and Hashcat, in uncovering hashed passwords from both Linux and Windows systems. The ability to crack these hashes highlights the importance of using strong, complex passwords and regularly updating them to mitigate the risk of unauthorized access.

## References
- John the Ripper. (n.d.). John the Ripper [Software]. Retrieved from https://www.openwall.com/john/
- Hashcat. (n.d.). Hashcat [Software]. Retrieved from https://hashcat.net/hashcat/
