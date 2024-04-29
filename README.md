# Active Directory

## Objective
In this project you will see how organizations manage their resources such as
users, computers and groups.This project will showcase how to install an active 
directory. It will show how to create a splunk instance where it will be 
ingesting events from a windows server, this windoows server will hold the active 
directory. You will also seeevents ingested from the target windows machine that
uses sysmon which is a windows system service and device driver that logs system 
activity to the Windows event log. The project will then move on to perform a
brute force attack using Kali Linux as our attacking machine to see what telemetry 
it generates. This project will also use atomic redteam aswell.



### Skills Learned

- Understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Knowledge of network protocols and security vulnerabilities.


### Tools Used

- Splunk (SIEM) system for log ingestion and analysis.
- Windows 10 OS system for target machine.
- Windows server for Active Directory.
- Kali Linux for attacking machine.
- Splunk Universal Forwarder for sending data over to our Splunk server.
- Sysmon for generating telemetry to send over to Splunk.
  
## Steps

1. [Create our logical diagram.](https://github.com/FrancisDunne/Active_Directory/blob/main/Diagram.pdf)

   ![Logical Diagram](https://img.shields.io/badge/-Logical%20Diagram-0000FF?style=for-the-badge)

3. [After downloading necessary tools we then need to configure the network.](https://github.com/FrancisDunne/Active_Directory/blob/main/Nat%20Network%20setup.png)

   ![NAT Network Setup](https://img.shields.io/badge/-NAT%20Network%20Setup-0000FF?style=for-the-badge)

5. [Set up the static IP for Splunk.](https://github.com/FrancisDunne/Active_Directory/blob/main/Static%20IP%20for%20Splunk.png)
   ![Static IP for Splunk Server](https://img.shields.io/badge/-Static%20IP%20for%20Splunk%20Server-0000FF?style=for-the-badge)

6. [Upload Splunks download to Ubuntu and start.](https://github.com/FrancisDunne/Active_Directory/blob/main/Upload%20splunk%20download%20to%20Ubuntu.png)
   ![Upload Splunk download to Ubuntu](https://img.shields.io/badge/-Upload%20Splunk%20download%20to%20Ubuntu-0000FF?style=for-the-badge)

7. [Configure the Target machine static IP.](https://github.com/FrancisDunne/Active_Directory/blob/main/Configure%20Target%20machines%20static%20IP.png)
   ![Target Machine static IP](https://img.shields.io/badge/-Target%20Machine%20static%20IP-0000FF?style=for-the-badge)

Each step includes a hyperlink and a badge. Adjustments can be made if needed.



