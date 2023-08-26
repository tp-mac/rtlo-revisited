# Looking from Right to Left - RTLO Attacks Revisited
REDTEECON 1 Conference Talk (18th August 2023)
- Researchers
  - Chong Kai Jie
  - Isaac Ethan Chua

## Overview of Research
Right-to-Left-Override (RTLO) is a Unicode character with the codepoint of U+202E which is used to write languages read from right to left. Our research allowed us to understand that the RTLO character can be implemented through the Character Map in Windows or in Visual Studio Code by typing “/u202e”. Our research on RTLO attacks mainly comprised attacks on file extensions and URLs. Applying the RTLO character in text causes any text written behind it to appear in reverse. 

## Additional sub topics
RTLO attacks on URLs: 
Our research on RTLO helped us to understand how the RTLO character can be applied in URLs to conduct an attack. Through our research, we created a proof-of-concept (POC) of a phishing attack conducted through a link to a domain, moc.elgoog, with RTLO applied to the front of it. The domain was created on a DNS server on a Windows Server 2019 virtual machine. Attached are the code files and the SQL file created for this POC. 
To connect to the domain for this POC, point the DNS server of any client virtual machine to the IP address of the DNS server. 

Requirements: 
Windows Server 2019 VM with XAMPP 

Other configurations: 
For the code files created to be displayed, create a folder named e.g. testingrtlo in C:\xampp\htdocs and place the files in that folder. 
Edit the httpd-vhosts file in C:\xampp\apache\conf\extra with this 3 lines: 

"<VirtualHost *:80>
          DocumentRoot C:/xampp/htdocs/testingrtlo 
</VirtualHost>"

RTLO attacks on File extensions:
Through the research on RTLO, we applied our understanding by creating a RTLO file extension type of attack. In it we created a proof of concept(imagest.py) of the RTLO file extension attack whereby file exclusions would be discreetly added to avoid RTLO flagging. Iteration 2(install2.py) are attempts at applying it maliciously. Iteration 3(1stage.py and install.py) works as a stager attack and are as close as we got to an effective working attack. The executables for testing are stored in DIST folder.

Requirements:
7zip is required for iteration 3 script to work.

## References/Links
- Put your references here
