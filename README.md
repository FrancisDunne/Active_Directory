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

1. Create our logical diagram.
