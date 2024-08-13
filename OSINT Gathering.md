# Open Source Intelligence Gathering

## Abstract
Throughout the information gathering process, Maltego was used by running transforms on different entities within the Tintictech organization. This provided a graphical interface with a layout of the organization’s infrastructure. Dig was a tool used to gather more information pertaining to the domains DNS query. Through this tool, more information on the DNS and Mail server’s addresses were uncovered. The next tool used was DNSENUM, which disclosed host names, server names, and other services. The Harvester was then used to brute force a long list of common DNS names to test the provided domain for any subdomains.

## List of Figures
- **Figure 1**: Kali VM
- **Figure 2**: Maltego Transform
- **Figure 3**: Tintictech Addresses
- **Figure 4**: DNS Shodan Transform
- **Figure 5**: DNS Table
- **Figure 6**: Shodan Tags
- **Figure 7**: Dig Output
- **Figure 8**: Dig Mail Server Output
- **Figure 9**: DNSENUM Server Output
- **Figure 10**: DNSENUM PHP
- **Figure 11**: Whois Query
- **Figure 12**: theHarvester

## Introduction
This report was developed using different passive reconnaissance tools such as Maltego, Dig, DNSENUM, and the Harvester. The purpose of using passive reconnaissance is to gather open-source information specific to our target. The tools used are a form of Open-Source Intelligence (OSINT) which allows me to access underlying information, without being detected. Performing these tasks provided me with crucial information, that I can then use to exploit in further phases of this penetration test.

## Kali VM

![image](https://github.com/user-attachments/assets/2692ee93-499a-494d-bcc3-f827227c0da1)
**Figure 1**: Kali VM


## Maltego
Using Maltego, we can search multiple open-source intelligence feeds for information on a target. The information is then displayed on an interactive graphical interface. Running a Transform on Tintictech’s website, we receive a variety of different outputs, such as IP addresses, a DNS Server, and different social media accounts related to Tintictech.

![image](https://github.com/user-attachments/assets/26e4cbef-c7ec-4227-8a02-ce165aa714ab)
**Figure 2**: Maltego Transform


One rather interesting output is from Pastebin.com, which is used as an online service where users can store plain text, such as source code snippet. The link provided by Maltego takes us to a page that has a list of accounts with tintictech.com domains. If these email addresses are part of the organization, then we could use these in future tests such as phishing campaigns.

![image](https://github.com/user-attachments/assets/ad21a25d-dcca-41ac-b015-7a3960ac526a)
**Figure 3**: Tintictech Addresses


Now that we know tintictech.com is a valid DNS Server, we can dig a little deeper by running the Shodan transform on that server. We can now see a variety of subdomains/servers along with some underlying configurations (e.g., dmarc, spf, google-verified). We can also see an IP address which we can further investigate. Knowing these subdomains/servers can lead to different web-based attacks, and knowing these configurations can lead to specific evading techniques.

![image](https://github.com/user-attachments/assets/b2fab590-b60b-4ed9-910c-082090e2602b)
**Figure 4**: DNS Shodan Transform

![image](https://github.com/user-attachments/assets/c30c858f-b058-4a12-b4b1-e92eb28b96c5)
**Figure 5**: DNS Table

![image](https://github.com/user-attachments/assets/e16a631f-16dc-4f54-9fed-f2f697dcd7a6)
**Figure 6**: Shodan Tags


## Dig
Dig is used as a command line tool, to query DNS. In this example, I ran Dig against the known tintictech.com DNS server. In the output, we can see that the output includes details like the queried server, time to live (TTL), record type, and associated IP address.

![image](https://github.com/user-attachments/assets/5d770eb9-b394-41d4-803d-1d57b71b91e4)
**Figure 7**: Dig Output


Dig can also be used to query mail servers, using the “mx” switch. In the output, we can see that Tintictech is using an Outlook mail server. This can be useful to a threat actor as they now know the targets mail server and its address.

![image](https://github.com/user-attachments/assets/7862f48c-ff0f-4109-84b3-e64da818d52b)
**Figure 8**: Dig Mail Server Output


## DNSENUM
This tool will run different queries against a domain. I used the “-v” switch for verbose, “-r” for recursion on subdomains, and “-w” to perform whois. It first displays the host addresses, name servers, and mail servers.

![image](https://github.com/user-attachments/assets/cae6d8b1-22de-49f9-9acd-7a5c10ae6da0)
**Figure 9**: DNSENUM Server Output


We then find something interesting when searching through the output. There is a php.myadmin.tintech.com server, indicating that php is in use. This could be a future point of entry if a php exploit is available or created.

![image](https://github.com/user-attachments/assets/93bc2428-28a5-45c3-82e4-4eb789adbbfd)
**Figure 10**: DNSENUM PHP


The whois query responds with two IP addresses and their subnets. We can use this information to further investigate these addresses and find possible vulnerabilities.

![image](https://github.com/user-attachments/assets/dd0d7493-c090-4320-80b8-a6940e38c0b6)
**Figure 11**: Whois Query


## theHarvester
Using theHarvester, a DNS brute force against 4989 words was ran. This will provide a list of possible DNS servers. In this output, we can see the response did not find any IP’s, email addresses, or hosts, but it did find a list of possible DNS services. I can use these findings to test for any open webpages or possible vulnerabilities.

![image](https://github.com/user-attachments/assets/ae7e2d0c-802d-4ee2-9e59-db0d8152bf13)
**Figure 12**: theHarvester


## Methodology
This report focuses on passive reconnaissance methodologies. Throughout these tests, the focus was on gathering as much information as possible without leaving a digital footprint. Using a variety of OSINT tools, information can be gathered and reviewed, to then use in future phases of a penetration test.


## Conclusions and Recommendations
When considering that this information was all found using OSINT tools, there are a variety of techniques that can be used to redact information or minimize the company’s digital footprint. It is best practice to routinely perform information gathering tests to see what information is readily available to adversaries. However, there are certain systems that cannot be hidden from the public. Implementing secure protocols on outward facing servers can be beneficial in evading adversaries and protecting crucial systems.


## References
- DNSENUM. (n.d.). DNSENUM [Software]. Retrieved May 20, 2024, from https://github.com/fwaeytens/dnsenum/
- Edge, M. (2024). theHarvester: Open-source intelligence tool [Software]. GitHub. https://github.com/laramies/theHarvester
- Internet Systems Consortium. (n.d.). Dig (DNS tool). Retrieved May 20, 2024, from https://www.isc.org/dig/
- Paterva. (2024). Maltego [Software]. Paterva. https://www.paterva.com
