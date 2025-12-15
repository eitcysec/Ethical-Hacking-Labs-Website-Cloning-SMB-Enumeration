# Ethical-Hacking-Labs-Website-Cloning-SMB-Enumeration
This repository documents two ethical hacking labs conducted for educational purposes

PART 1: Website Cloning Lab (SETOOLKIT)
🔧 Lab Setup
Attacker Machine: Kali Linux
Target: A local test website (http://dvwa.vm)

Step-by-Step Procedure
1️⃣ Launch SETOOLKIT
sudo  setoolkit

<img width="857" height="424" alt="image" src="https://github.com/user-attachments/assets/4da0813a-8037-492f-88e4-f007085cc7a6" />


2️⃣ Select Attack Type
1) Social-Engineering Attacks

<img width="941" height="418" alt="image" src="https://github.com/user-attachments/assets/fdb97854-0330-4a5d-b88e-028e37a7d1d9" />





3️⃣ Select Vector
2) Website Attack Vectors

<img width="958" height="416" alt="image" src="https://github.com/user-attachments/assets/1efc1c6d-a54a-4de5-96c6-893219795dd5" />



4️⃣ Select Attack Method
3 ) Credential Harvester Attack Method

<img width="926" height="419" alt="image" src="https://github.com/user-attachments/assets/2ef6e912-18ef-4ab0-bb95-e8c4784b0b6f" />



5️⃣ Select Cloning Option
2) Site Cloner

<img width="925" height="424" alt="image" src="https://github.com/user-attachments/assets/653b90ed-4004-4014-83ba-6f49ab67f723" />


6️⃣ Enter Attacker IP
ifconfig

<img width="932" height="433" alt="image" src="https://github.com/user-attachments/assets/0065107a-fe12-4885-a00a-3e4f9dbd12fc" />

Use your Kali IP (e.g. 192.168.56.101) In this lab we are using the br-internal adapter which has IP 10.6.6.1

<img width="944" height="419" alt="image" src="https://github.com/user-attachments/assets/2dd4dc77-ed39-487a-9b20-22afd59ec24f" />


7️⃣ Enter Target URL

We will be using the in-bult website http://dvwa.vm

<img width="948" height="419" alt="image" src="https://github.com/user-attachments/assets/f93ba419-59bc-42ed-a8ba-b8f120b5fe17" />




SETOOLKIT will:
Clone the website
Host it locally

<img width="475" height="391" alt="image" src="https://github.com/user-attachments/assets/e6e2a481-52cb-4c45-86f2-5f7afdd2bcc0" />


Capture submitted credentials

<img width="952" height="419" alt="image" src="https://github.com/user-attachments/assets/31d22001-2cd6-469f-855a-36b73bf6b2c9" />


PART 2: SMB Vulnerability Scanning (Enum4Linux)
🔧 Lab Setup
Attacker: Kali Linux
Target: Metasploitable2

Step-by-Step Procedure
1️) Scan the subnet to check for live hosts that have SMB protocol running
Command: nmap -sN 172.17.0.0/24

<img width="932" height="416" alt="image" src="https://github.com/user-attachments/assets/b11d8c0c-486a-4ab6-81b5-a9606c430e88" />


2️) Basic Enum4Linux Scan
enum4linux -U to get get userlist

<img width="946" height="386" alt="image" src="https://github.com/user-attachments/assets/cce266dc-9709-4520-a8b5-aaef07c51b15" />

<img width="931" height="419" alt="image" src="https://github.com/user-attachments/assets/5c9cfc48-b35a-4a6b-9a0f-423628249d51" />

<img width="929" height="419" alt="image" src="https://github.com/user-attachments/assets/eab1f18a-8095-4d6b-810e-959302833226" />


3️) Detailed Enumeration
enum4linux -M  172.17.0.2      get machine list*
<img width="939" height="413" alt="image" src="https://github.com/user-attachments/assets/7aa5f3ee-63df-4ce0-a7dc-a0b6ab0e7a8f" />


-S get a list of file shares

<img width="731" height="411" alt="image" src="https://github.com/user-attachments/assets/17f4a5fa-16fc-4ef5-8621-1ffb7d17a89c" />

<img width="688" height="424" alt="image" src="https://github.com/user-attachments/assets/70b60bb9-b6f2-4c33-8e94-0adf0d246c33" />

-G get a list of the groups and their members

<img width="868" height="260" alt="image" src="https://github.com/user-attachments/assets/6c1ff901-f9a3-4d57-9f97-85a6df3409e6" />

-P list the password policies

<img width="802" height="419" alt="image" src="https://github.com/user-attachments/assets/91d1b8e7-0481-4593-ac43-1363c34c2e1e" />

-i get a list of printers

<img width="852" height="376" alt="image" src="https://github.com/user-attachments/assets/dea8ce43-4e32-40c3-a270-26eea342239d" />

**The smbclient -L command to list the shares on the target host. **
Command: smbclient -L //172.17.0.2/

<img width="920" height="358" alt="image" src="https://github.com/user-attachments/assets/f356acd9-7dad-471b-8022-eaae3b933187" />

**Connect to the tmp share using the smbclient command by specifying the share name and IP address.
**

smbclient //172.17.0.2/tmp

<img width="848" height="419" alt="image" src="https://github.com/user-attachments/assets/9bfa7b6f-9aad-44ca-9564-c1085ca93f94" />

Upload the badfile.txt to the target server using the put command. The syntax for the command is:
put local-file-name remote-file-name

<img width="850" height="418" alt="image" src="https://github.com/user-attachments/assets/9d7cb27e-5cdc-492e-8aa8-7b926d1aa8df" />



**What Enum4Linux Enumerates**
SMB shares,
User accounts.
Groups,
OS information,
Password policy,



