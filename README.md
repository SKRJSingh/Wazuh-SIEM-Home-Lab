# SIEM Lab

## Objective

The objective of this lab was to build and configure a Security Information and Event Management (SIEM) environment using Wazuh. The lab focused on deploying a centralized Wazuh manager and dashboard, configuring agents across multiple operating systems, collecting security telemetry, generating endpoint activity, and analyzing alerts through the Wazuh dashboard.

The environment included an Ubuntu endpoint, Windows user endpoint, and Windows Server, providing hands-on experience with centralized security monitoring across different operating systems.
### Skills Learned

• Deployed and configured a Wazuh SIEM environment.

• Deployed and configured Wazuh agents on Ubuntu, Windows, and Windows Server systems.

• Configured endpoints to communicate with the Wazuh manager.

• Collected and monitored security telemetry from multiple operating systems.

• Analyzed Wazuh alerts and investigated detected activity.

• Used the Wazuh dashboard to search and interpret security events.

• Developed an understanding of centralized log collection and SIEM alerting.

• Practiced identifying suspicious activity through endpoint security data.

• Gained experience monitoring a multi-endpoint security environment.

### Tools Used

• Wazuh — SIEM and endpoint security monitoring platform.

• Ubuntu — Used to host the Wazuh manager and dashboard and monitor an Ubuntu endpoint.

• Windows — User endpoint monitored using the Wazuh agent.

• Windows Server — Server endpoint monitored using the Wazuh agent.

• Wazuh Agent — Installed on monitored endpoints to collect and forward security telemetry.

• Wazuh Dashboard — Used to monitor endpoints, analyze events, and investigate alerts.

## Steps
I started with obtaining a VM with Ubuntu. At first I did this with Ubuntu 26.04, but later had compatibility issues with Wazuh, so I had to revert to an older version of Ubuntu such as 24.04.

After setting up Ubuntu, I opened the terminal and gave myself admin privileges with sudo bash and installed curl. Next, I used the Quick Install directions to install Wazuh with a copy paste command. 

I encountered a problem at the end of the installation process, and I had to do some digging with the command "sudo grep -i -C 5 "error\|failed" /var/log/wazuh-install.log". which allowed me to search through the Wazuh installation log file to help find and troubleshoot the error that happened during the installation process. I found out that I was running out of storage during the installation process, so I cleared some space and reinstalled, and it worked.

(Image 1: Showcasing troubleshooting of Wazuh installation failure and solution)
<img width="761" height="487" alt="Screenshot 2026-08-10 184244" src="https://github.com/user-attachments/assets/b84de6b5-0a3b-4bfd-b0e6-cc2557ac3479" />


After the installation, I could access Wazuh using its IP and the given credentials. Then, I deployed agents. I deployed an agent on another Ubuntu user, utilizing the terminal to enter the given commands. I deployed 2 agents on a Windows User and one on a Windows Server using Admin PowerShell. After this I was able to see the agents on my Wazuh dashboard and I started downloading and generated endpoint activity to produce security telemetry in the agents to create some noise. 

(Image 2: Showcasing Wazuh dashboard after generating user activity across agents)
<img width="1270" height="837" alt="Screenshot 2026-08-11 173026" src="https://github.com/user-attachments/assets/bf9ee181-604e-45d1-a923-0de0007abf63" />


I then went on my Windows User and entered the wrong password multiple times to simulate repeated failed authentication attempts. I was alerted, and able to monitor and document the incident. 


(Image 3: Showcasing alerts received from failed authentication attempts)
<img width="1275" height="491" alt="Screenshot 2026-08-11 172957" src="https://github.com/user-attachments/assets/0946eb7d-105e-4bb8-9b03-867e4e95c5c6" />


## Results

The lab successfully demonstrated the deployment and operation of a centralized Wazuh SIEM environment across Ubuntu, Windows, and Windows Server endpoints.

Security telemetry from multiple systems was collected and analyzed through the centralized Wazuh dashboard, providing hands-on experience with SIEM deployment, endpoint monitoring, centralized logging, security alert analysis, and investigation.

