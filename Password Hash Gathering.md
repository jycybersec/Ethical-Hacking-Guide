# Password Hash Gathering

## Abstract
Throughout the password hash gathering process, various exploits were used on different virtual machines within the lab environment. This provided a practical understanding of how to gather hashed passwords from different systems. The vsFTP vulnerability was used to access the Linux machine's command line and transfer the `/etc/shadow` file. The psex exploit was used on the Windows XP machine to pull user hashes, and the eternalblue exploit was used on the Win2k8 machine to pull user hashes.

## Introduction
This report was developed using different exploits to gather hashed passwords from three different virtual machines. The purpose of this exercise is to understand the importance of patching and removing vulnerable services/applications. Performing these tasks provided me with crucial information that can be used to understand the security posture of these systems.

## Kali VM
Kali IP: 192.168.48.129

## Metasploitable Linux VM
Metasploitable Linux IP: 192.168.48.130

## Metasploitable Win2k8 VM
Metasploitable Win2k8 IP: 192.168.48.132

## Windows XP VM
Windows XP IP: 192.168.48.131

### Metasploitable Linux passwords shadow file:

- The Metasploitable Linux machine is hosting a vulnerable service (vsFTPD 2.3.4). so we'll use a Metasploit payload to create an initial connection.
![image](https://github.com/user-attachments/assets/f1646622-e8d6-4d1f-8c49-0c24840544bf)

- The shadow file found in `/etc/` on Linux operating systems, contains user names, along with their corresponding hashes. We will transfer the shadow file to our Kali VM using Netcat.
![image](https://github.com/user-attachments/assets/69a862b1-d563-457d-858f-2242a5b36bdb)

- Shadow file recieved on Kali VM
![image](https://github.com/user-attachments/assets/c8d2756b-b0b9-4394-8b73-4ad263065b41)


### Win2k8 hashes file or SAM dump (hashdump):

- EternalBlue is a known vulnerability found on Win2k8 servers. We'll use a Metasploit EternalBlue SMB exploit to gain an initial connection.
![image](https://github.com/user-attachments/assets/1b0b1a32-5d22-4761-aa94-b46a892fa19a)

- This image displays the output of the hashdump command on the Win2k8 machine, showing the gathered LM/NTLM hashes.
![image](https://github.com/user-attachments/assets/dab7a159-0f1c-4cc9-87b3-3e4f5c83f053)

### Windows XP hashes file or SAM dump (hashdump):

- psexec is a known vulnerability found in Windows XP machines. We'll use a Metasploit psexec payload to create an initial connection.
![image](https://github.com/user-attachments/assets/6bbc1f43-ca83-4c66-bfec-886740d10481)

- This image shows the result of the hashdump command on the Windows XP machine, listing the user hashes.
![image](https://github.com/user-attachments/assets/321a3c45-8d5d-4bbb-b034-b1eaad03b5c9)

## Methodology
This report focuses on gathering hashed passwords from different virtual machines using various exploits. The focus was on understanding the vulnerabilities and how they can be exploited to gather sensitive information. Using a variety of exploits, information was gathered and reviewed to understand the security posture of these systems.

## Conclusions and Recommendations
When considering that this information was all found using various exploits, there are a variety of techniques that can be used to secure systems. It is best practice to routinely perform security assessments to identify and mitigate vulnerabilities. Implementing secure protocols and keeping systems up to date can be beneficial in protecting crucial systems.

## References
- Metasploit. (n.d.). Metasploit [Software]. Retrieved from https://www.metasploit.com/
