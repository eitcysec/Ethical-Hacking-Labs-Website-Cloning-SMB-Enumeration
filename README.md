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






