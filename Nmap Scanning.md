# Network Port Scanning – Nmap

## IP Addresses:
- **Kali**: 192.168.48.129
- **Metasploitable Linux**: 192.168.48.130
- **Metasploitable Win2k8**: 192.168.48.132
- **Windows XP**: 192.168.48.131

## Abstract
In this project, Nmap is used to scan three virtual machines (VMs) from a Kali VM. The scans aim to identify open ports, services, and potential vulnerabilities. The results were captured and analyzed to understand the network infrastructure and security posture of the VMs.

## Introduction
This report details the process of using Nmap for network port scanning and vulnerability assessment. The objective was to perform active reconnaissance on three VMs using various Nmap switches and capture the results for analysis.

## Kali VM
The Kali VM was used as the primary tool for conducting the scans. It provided the necessary environment and tools for network scanning and analysis.

## Nmap Scans
### Commands Used:
1. `sudo nmap -sV -O x.x.x.x`  
   - Scans the VM for open ports and services, and attempts to identify the operating system.
2. `sudo nmap -sV -O -A x.x.x.x`  
   - Performs a more aggressive scan, including version detection, script scanning, and traceroute.
3. `sudo nmap -sV -O -sC x.x.x.x`  
   - Includes default scripts in the scan.

### Results:
#### MSF Linux:

The initial scan on MSF Linux reveals several open ports and services.
![image](https://github.com/user-attachments/assets/170c8e44-34dc-4b69-badd-b3fbfbd65d5c)

The aggressive scan provides detailed information on the operating system.
![image](https://github.com/user-attachments/assets/f5d895b5-75eb-4dae-9ad8-23269d684a41)
![image](https://github.com/user-attachments/assets/0787d574-32f4-48fd-ba01-11315119d8dd)
![image](https://github.com/user-attachments/assets/da6d8abf-493a-49eb-90d3-12a74eab008c)

Script scanning identifies additional potential security issues.
![image](https://github.com/user-attachments/assets/25656e47-2724-4694-8ca6-f3bf57fa4e40)
![image](https://github.com/user-attachments/assets/4d59dbcc-76ab-47d2-802a-a2cc55f1000a)


#### MSF Win2k8:

The initial scan on MSF Win2k8 reveals several open ports and services.
![image](https://github.com/user-attachments/assets/c4dd15ca-fe57-423f-8902-9205c3d4c328)
![image](https://github.com/user-attachments/assets/3595bd78-6337-43ee-b057-b088e902c6a0)

The aggressive scan provides detailed information on the operating system.
![image](https://github.com/user-attachments/assets/9de76a0f-acd3-4fbe-bf64-76ceb2a0b2de)

Script scanning identifies additional potential security issues
![image](https://github.com/user-attachments/assets/1dc07be7-b5f6-44a0-9e41-c6bf97ab4ab9)
![image](https://github.com/user-attachments/assets/dbc3419a-17d5-42b5-8a82-4b35dd986973)
![image](https://github.com/user-attachments/assets/3d944ffd-4b5d-4c39-99c5-acae5d067bfe)


#### Win XP:

The initial scan on Win XP reveals several open ports and services.
![image](https://github.com/user-attachments/assets/bbf71475-17e8-494d-b6c3-0c15f4b9a7bd)

The aggressive scan provides detailed information on the operating system.
![image](https://github.com/user-attachments/assets/cd769ddb-684d-4fda-88e2-96bde8a1eed7)
![image](https://github.com/user-attachments/assets/491ef29e-9408-4c58-98e6-395b9505f7e3)

Script scanning identifies additional potential security issues.
![image](https://github.com/user-attachments/assets/fff41090-37c2-4b44-8676-3cdbbbd1aff2)
![image](https://github.com/user-attachments/assets/f2b4de9a-2366-495a-854e-c525645060d3)


## Common Vulnerabilities and Exposures (CVEs)
To identify CVEs, the following Nmap command was used:
`sudo nmap -sV -O --script=vulners x.x.x.x`

This scan provides detailed information on each vulnerability, including its severity and potential impact. By analyzing these results, we aim to understand the security posture of each system and identify areas that require remediation.

### Results:
#### MSF Linux:
![image](https://github.com/user-attachments/assets/9e2455a9-3494-4f89-a99c-f64367a1b5c4)
![image](https://github.com/user-attachments/assets/aea26a66-29ac-4370-82f4-116237546ae3)
![image](https://github.com/user-attachments/assets/98e3d0ed-b658-4dbf-b478-5449ae5fbeaa)
![image](https://github.com/user-attachments/assets/7e986ac5-0a90-4cbd-9185-de41b42cb45d)
![image](https://github.com/user-attachments/assets/cc6baea7-1d9a-40e2-b597-a1ff7552930d)
![image](https://github.com/user-attachments/assets/807fd7a1-e385-4f34-9b75-8420d43b80f9)
![image](https://github.com/user-attachments/assets/7ea6deaf-83dc-44f2-b45f-78b53b478947)
![image](https://github.com/user-attachments/assets/b4f2d05c-5292-4ee1-942d-afd0447f0b55)
![image](https://github.com/user-attachments/assets/1811db70-bc8b-4a69-a312-ddf594c9d5a5)
![image](https://github.com/user-attachments/assets/b067339e-8dcd-4155-a427-4a8f82109484)


#### MSF Win2k8:
![image](https://github.com/user-attachments/assets/51e89b7c-e3b1-46bb-ac1f-b033bbb58918)
![image](https://github.com/user-attachments/assets/792c1298-5a86-4576-81f3-29d2b5d934d6)
![image](https://github.com/user-attachments/assets/38d2ccd3-12d7-4a0b-9e88-93c16f2143c1)
![image](https://github.com/user-attachments/assets/7642f53b-cc81-4a3e-aac6-f938e61f5786)
![image](https://github.com/user-attachments/assets/f1626573-f6a9-49dd-8101-299d81310378)


#### Win XP:
![image](https://github.com/user-attachments/assets/9148a068-1127-48c5-9ad9-9c1523f7ddb4)
![image](https://github.com/user-attachments/assets/29c3998a-1434-490e-8154-ed1ca7e420e1)
![image](https://github.com/user-attachments/assets/3f6dbfbc-e306-4a46-89dd-23df1b422042)
![image](https://github.com/user-attachments/assets/734f053f-6776-469b-bd88-bf0de6d1cade)
![image](https://github.com/user-attachments/assets/43d5474f-fcad-411b-9a6c-c16f19ade90f)
![image](https://github.com/user-attachments/assets/007d9cb7-37a2-44be-bd53-8cda690fce2e)
![image](https://github.com/user-attachments/assets/922f86c8-2f99-4f95-aae1-027c585bd432)


## Methodology
This project involved using Nmap with various switches to perform detailed scans of three VMs. The scans included service detection, OS detection, and vulnerability assessment. The results were captured and analyzed to identify successful and failed connections, destination IP addresses, ports, protocols, and services.

## Summary
We started off by using the `-sV` switch to perform a verbose scan, along with `-O` to enable operating system detection. We then utilized the `-A` switch to leverage version detection, script scanning, traceroute, along with OS detection. The next script utilized the `-sC` switch to include a default script. When scanning for vulnerabilities using the vulners script, I was surprised to see the amount of known CVEs on each machine. I expected there to be a large amount on the metasploitable machines, but the amount on the Windows XP machine was almost identical. This goes to show how dangerous legacy systems that are EOL can be. Nmap is a well-known tool used within the world of cybersecurity to perform active reconnaissance and port scanning.

## References
- Nmap. (n.d.). Nmap [Software]. Retrieved May 20, 2024, from https://nmap.org/
