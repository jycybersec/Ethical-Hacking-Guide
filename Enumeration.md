# Enumeration Assignment

## IP Addresses
- **Kali**: 192.168.48.129   
- **Win XP**: 192.168.48.131 
- **Win 2k8**: 192.168.48.132  

## Crackmapexec
Crackmapexec is a post-exploitation tool that helps automate the assessment of large Active Directory networks. It can be used to enumerate shares, users, and disks on a target machine. The -u switch specifies the username and -p specifies the password.

### Win XP:
- **Shares**:
![image](https://github.com/user-attachments/assets/d3a2aefc-976d-43ad-aa4c-e281ae012512)
  - Identifies shared directories and files on the Windows XP machine.
  
- **Users**:
![image](https://github.com/user-attachments/assets/eaaf7f0f-3fcd-47cc-a067-cac2665e707b)
  - Lists the user accounts present on the Windows XP machine.
  
- **Disks**:
![image](https://github.com/user-attachments/assets/f67835f2-6a08-40ae-823f-b88be0244c4a)
  - Displays information about the disk drives on the Windows XP machine.

### Win 2k8:
- **Shares**:
![image](https://github.com/user-attachments/assets/b4545c6f-66f7-401a-98d8-b1a2a3bf17d2)
  - Identifies shared directories and files on the Windows 2k8 machine.
    
- **Users**:
![image](https://github.com/user-attachments/assets/b555b4a8-4f53-4e89-8517-81b13f7f04ca)
  - Lists the user accounts present on the Windows 2k8 machine.
    
- **Password Policy**:
![image](https://github.com/user-attachments/assets/964b862c-2faf-4b3c-8038-78b2938b16b2)
  - Displays the password policy settings on the Windows 2k8 machine.


## Rpcclient
Rpcclient is a utility that can be used to execute client-side MS-RPC functions. It is useful for gathering information about users, shares, and other system details.

### Win XP:

![image](https://github.com/user-attachments/assets/3fbec454-0b1e-4e35-a31c-2a49ec2bdb0b)

- **Users**:
![image](https://github.com/user-attachments/assets/3135cba7-0e2c-4b4f-b4fa-ca5a9be76789)
  - Retrieves a list of user accounts on the Windows XP machine.
    
- **Shares**:
![image](https://github.com/user-attachments/assets/47ca3095-374a-45f7-9028-2605b72e5544)
  - Identifies shared directories and files on the Windows XP machine.
    
- **LSA Query**:
![image](https://github.com/user-attachments/assets/d1dc8268-e86a-42b9-b14e-ab2bc62e1994)
  - Queries the Local Security Authority (LSA) for security-related information.

### Win 2k8:

![image](https://github.com/user-attachments/assets/f3396250-872b-4c9f-a8cc-169111577961)

- **Users**:
![image](https://github.com/user-attachments/assets/4ad4c8e7-079d-4d9a-90b8-109bc88c3f61)
  - Retrieves a list of user accounts on the Windows 2k8 machine.
    
- **Shares**:
![image](https://github.com/user-attachments/assets/50781b0e-4bf5-44da-90b4-a16f3f8d060d)
  - Identifies shared directories and files on the Windows 2k8 machine.
    
- **Display info**:
![image](https://github.com/user-attachments/assets/2e7933f6-cd3a-48be-afcb-faed175b2116)
  - Displays system information about the Windows 2k8 machine.


## Enum4linux
Enum4linux is a tool for enumerating information from Windows machines using the SMB (Server Message Block) protocol. It can gather details about users, shares, and SIDs (Security Identifiers). 

- **Users**:
![image](https://github.com/user-attachments/assets/718e0d3c-7b66-454b-99fc-70c565194b6e)
![image](https://github.com/user-attachments/assets/e456b464-bc21-4ae1-86d8-b501c25237b8)
  - Lists the user accounts present on the Windows XP machine.

- **SID**:
![image](https://github.com/user-attachments/assets/cc05b715-edfa-4e5d-b2eb-a75270e80577)
![image](https://github.com/user-attachments/assets/a7b2ca3e-fb8e-4e7a-81a7-7553501097a1)
  - Retrieves the Security Identifier (SID) for the Windows XP machine.
    
- **Shares**:
![image](https://github.com/user-attachments/assets/172bbd4a-c136-4d73-8856-eefe53b9683f)
![image](https://github.com/user-attachments/assets/3c2ff6b1-e5b1-4c87-b455-91a05936614d)
  - Identifies shared directories and files on the Windows XP machine.

### Win 2k8:
- **Users**:
![image](https://github.com/user-attachments/assets/3a5e6036-e526-4dd2-9ee4-fb591de59e7b)
![image](https://github.com/user-attachments/assets/a258316e-bbfe-4b47-b0e1-a593d449cefb)
  - Lists the user accounts present on the Windows 2k8 machine.
    
- **SID**:
![image](https://github.com/user-attachments/assets/962353ed-8b99-4cfb-9856-9a129ff56b72)
![image](https://github.com/user-attachments/assets/31ad5d15-44e9-4c25-9c57-7699253c4220)
- Retrieves the Security Identifier (SID) for the Windows 2k8 machine.
  
- **Shares**:
![image](https://github.com/user-attachments/assets/7662ec21-855b-47c7-b3f3-474535eedcc4)
![image](https://github.com/user-attachments/assets/c189a6fa-ce7f-401e-ac83-a4ea4e4d999d)
- Identifies shared directories and files on the Windows 2k8 machine.


## Smbclient
Smbclient is a command-line tool that allows users to access SMB/CIFS resources on servers. It can be used to connect to shared directories and navigate through file shares.

### Win XP:
![image](https://github.com/user-attachments/assets/c16751d7-01f9-4b4c-bea2-bdfb3799f179)
  - Connects to the Windows XP machine and navigates through its shared directories.

### Win 2k8:
![image](https://github.com/user-attachments/assets/99506bf5-4b4c-41b5-82d4-d39f60879032)
  - Connects to the Windows 2k8 machine and navigates through its shared directories.

## Summary
Using Crackmapexec, we enumerated shares, users, and disks on both Win XP and Win 2k8 machines. Rpcclient was then utilized to gather detailed information about users, shares, and system details. Enum4linux provided further enumeration of users, shares, and SIDs on both machines. Finally, Smbclient allowed us to connect to and navigate through shared directories on both Win XP and Win 2k8. This comprehensive approach highlighted the importance of using multiple tools to gather extensive information about networked systems, emphasizing the vulnerabilities and shared resources that can be exploited in a cybersecurity context.

## References
- Crackmapexec. (n.d.). Crackmapexec [Software]. Retrieved June 6, 2024, from https://github.com/byt3bl33d3r/CrackMapExec
- Rpcclient. (n.d.). Rpcclient [Software]. Retrieved June 6, 2024, from https://www.samba.org/samba/docs/current/man-html/rpcclient.1.html
- Enum4linux. (n.d.). Enum4linux [Software]. Retrieved June 6, 2024, from https://github.com/CiscoCXSecurity/enum4linux
- Smbclient. (n.d.). Smbclient [Software]. Retrieved June 6, 2024, from https://www.samba.org/samba/docs/current/man-html/smbclient.1.html
