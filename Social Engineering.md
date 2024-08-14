# Social Engineering using SET

## Abstract
This report details the process of creating a social engineering page using the Social Engineering Toolkit (SET). The assignment involved cloning a login website, specifically the Google login page, and using it to capture credentials. The exercise provided insights into the effectiveness of social engineering attacks and the importance of URL accuracy and security warnings.

## Introduction
The purpose of this assignment was to understand the mechanics of social engineering attacks by using SET to create a phishing page. By cloning a legitimate login page and hosting it locally, the exercise demonstrated how attackers can deceive users into providing their credentials. This report outlines the steps taken, the tools used, and the lessons learned during the process.

## Kali VM
- Kali IP: 192.168.48.129

## Host File
- The Host file contains IP redirects or DNS translation, which in this case we'll use for our cloned website. We will use the name googlle.com (slightly misspelled) for possible typos or link redirect. We are not able to use google.com, because it is currently being used by that legitamite domain.
![image](https://github.com/user-attachments/assets/1192fe1a-3a9a-43a5-9564-e5e2563fd3eb)

## Social Engineering Toolkit (SET) Set Up
- After starting SET you will be prompted with your first option, we'll select "Social Engineering Attacks".
![image](https://github.com/user-attachments/assets/c2238426-fda1-4889-a85e-d548607a8743)

- The next option we will select is "Website Attack Vectors".
![image](https://github.com/user-attachments/assets/05bd037b-df86-49ca-ba2a-655b004ceb60)

- We want to perform a credential harvesting attack, so we will select option 3.
![image](https://github.com/user-attachments/assets/86e217bd-309a-4a23-bf32-fb341468c443)

- For the next option, we can either choose to clone a site, view available templates, or use a custom import. We'll select option 1 to view templates.
![image](https://github.com/user-attachments/assets/d3f1ab2c-b5ea-436a-b39c-0ee3bbcf89ab)

Confirm the POST address for the webpage (Kali IP) by clicking enter.
![image](https://github.com/user-attachments/assets/400c86ea-5699-4454-8f95-d81410528909)

- Out of the available templates, we'll choose the google option.
![image](https://github.com/user-attachments/assets/ee6b7abf-a9ac-4757-a83f-46e54a244415)


## Cloned Website
- The Google.com sign in page template can now be accessed via the machine IP or the Hostname added to the Host file.
![image](https://github.com/user-attachments/assets/4739a674-94a4-4685-939d-93e27695eae2)


## Captured Credentials
- Once credentials are entered and the sign in button is clicked, a POST message is sent to our Kali machine with the provided input.
![image](https://github.com/user-attachments/assets/df517ba3-d1e4-4c9d-b5a6-25609c4acbb6)


## Methodology
The methodology involved using SET to clone a legitimate login page and host it locally. The steps included configuring the host file to redirect traffic, setting up the cloned website, and capturing credentials entered by unsuspecting users. The exercise highlighted the importance of URL accuracy and the potential risks of unsecured warnings.

## Conclusions and Recommendations
This project underscored the effectiveness of social engineering attacks and the ease with which attackers can deceive users. To mitigate such risks, it is crucial to educate users about the importance of verifying URLs and recognizing security warnings. Regular training and awareness programs can help in reducing the success rate of phishing attacks.

## References
- TrustedSec. (n.d.). Social Engineering Toolkit (SET). Retrieved from https://www.trustedsec.com

