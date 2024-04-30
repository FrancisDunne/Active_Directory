# Active Directory

## Objective
In this project you will see how organizations manage their resources such as
users, computers and groups.This project will showcase how to install an active 
directory. It will show how to create a splunk instance where it will be 
ingesting events from a windows server, this windows server will hold the active 
directory. You will also see events ingested from the target windows machine that
uses sysmon, which is a windows system service and device driver that logs system 
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
  
## Steps

### Preparation

- Create the Logical Diagram:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Diagram.pdf" download>
      <img src="https://img.shields.io/badge/-Logical%20Diagram-0000FF?style=for-the-badge" />
    </a>


- After downloading neccessary tools we then need to configure the network:

   <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Nat%20Network%20setup.png">
      <img src="https://img.shields.io/badge/-NAT%20Network%20Setup-0000FF?style=for-the-badge" />
    </a>

## Splunk Server Config

- Set up the static IP for Splunk:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Static%20IP%20for%20Splunk.png">
        <img src="https://img.shields.io/badge/-Static%20IP%20for%20Splunk%20Server-0000FF?style=for-the-badge" />
    </a>


- Upload Splunks download to Ubuntu and start:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Upload%20Splunk%20to%20Ubuntu%20server.png">
        <img src="https://img.shields.io/badge/-Upload%20Splunk%20to%20Ubuntu%20server-0000FF?style=for-the-badge" />
    </a>

## Target Machine Config

- Configure the Target machine static IP:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Configure%20Target%20machines%20static%20IP.png">
        <img src="https://img.shields.io/badge/-Target%20Machine%20static%20IP-0000FF?style=for-the-badge" />
    </a>


- Download Splunk Forwarder to the target machine:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Download%20the%20splunk%20forwarder%20on%20target%20machine.png">
        <img src="https://img.shields.io/badge/-Downloaded%20Splunk%20Forwarder-0000FF?style=for-the-badge" />
    </a>


- Configuring sysmon on the target machine:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Sysmon%20Download.png">
        <img src="https://img.shields.io/badge/-Sysmon%20Download-0000FF?style=for-the-badge" />
    </a>


 - Create an input.conf in the local folder of the Splunk Forwarder:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Edit%20the%20input%20file.png">
        <img src="https://img.shields.io/badge/-Edit%20the%20input%20file-0000FF?style=for-the-badge" />
    </a>


- After editing the inputs file we need to change the log on status to this system and restart:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Change%20log%20on%20from%20This%20account%20to%20Local%20system%20account.png">
        <img src="https://img.shields.io/badge/-Change%20log%20on%20from%20This%20account%20to%20Local%20system%20account-0000FF?style=for-the-badge" />
    </a>


- Log into Splunk and add a new index file called endpoint referencing to the input.conf:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Create%20endpoint%20in%20indexes.png">
        <img src="https://img.shields.io/badge/-Create%20endpoint%20in%20indexes-0000FF?style=for-the-badge" />
    </a>


- Go to settings in splunk and configure the recieving to listen in on port 9997:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Configure%20recieving%20to%20port%209997.png">
        <img src="https://img.shields.io/badge/-Configure%20receiving%20to%20port%209997-0000FF?style=for-the-badge" />
    </a>


- Now we can search index=endpoint to see some events generated from our target machine:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Search%20index%3Dendpoint%20in%20the%20search%20bar%20in%20splunk.png">
        <img src="https://img.shields.io/badge/-Search%20index%3Dendpoint%20in%20the%20search%20bar%20in%20Splunk-0000FF?style=for-the-badge" />
    </a>

## Windows Server / Active Directory Config

- Now we need to do the same process for the Windows Server / Active Direwctory. We will configure the static IP:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Configure%20Windows%20Server%20Active%20Directory%20Static%20IP.png">
        <img src="https://img.shields.io/badge/-Configure%20Windows%20Server%20Active%20Directory%20Static%20IP-0000FF?style=for-the-badge" />
    </a>


- In the Windows Server we now need to install the Active Directory Domain Services in the Service Manager:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Install%20Active%20Directory%20Domain%20Services.png">
        <img src="https://img.shields.io/badge/-Install%20Active%20Directory%20Domain%20Services-0000FF?style=for-the-badge" />
    </a>


- Next we can promote our Server to a Domain Controller:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Promote%20the%20Windows%20Server%20to%20a%20Domain%20Controller.png">
        <img src="https://img.shields.io/badge/-Promote%20the%20Windows%20Server%20to%20a%20Domain%20Controller-0000FF?style=for-the-badge" />
    </a>


- We will now create some organizational units with users assigned to them:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Create%20an%20organizational%20unit%20and%20unit.png">
        <img src="https://img.shields.io/badge/-Create%20an%20organizational%20unit%20and%20unit-0000FF?style=for-the-badge" />
    </a>

## Connect to Domain Controller Via Target Machine

- We will head over to our target machine now and change our Dns settings to point to our Domain Controller:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Change%20Dns%20setting%20on%20Windows%20target%20.png">
        <img src="https://img.shields.io/badge/-Change%20DNS%20setting%20on%20Windows%20target-0000FF?style=for-the-badge" />
    </a>


- We can now join the Domain with our new user:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Join%20the%20domain%20with%20the%20new%20user.png">
        <img src="https://img.shields.io/badge/-Join%20the%20domain%20with%20the%20new%20user-0000FF?style=for-the-badge" />
    </a>


## Using Kali Linux to Perform a Brute Force Attack

- We will configure Kali Linux static IP:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Setting%20Kali%20Linux%20Static%20IP.png">
        <img src="https://img.shields.io/badge/-Setting%20Kali%20Linux%20Static%20IP-0000FF?style=for-the-badge" />
    </a>


- Next we will create a directory to store our files for our attack.
  We will use the tool named crowbar for our brute force attack.

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Install%20Crowbar.png">
      <img src="https://img.shields.io/badge/-Install%20Crowbar-0000FF?style=for-the-badge" />
    </a>


- We will use a wordlist built in on kali called rockyou and save it to our new directory we created:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Rockyou.png">
      <img src="https://img.shields.io/badge/-Rockyou-0000FF?style=for-the-badge" />
    </a>


- Next we will take the first 20 lines from our rockyou wordlist and save it to a password.txt file:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Save%2020%20lines%20to%20a%20password.txt%20file.png">
      <img src="https://img.shields.io/badge/-Save%2020%20lines%20to%20a%20password.txt%20file-0000FF?style=for-the-badge" />
    </a>


- We will go over to our target machine and enable remote desktop under our previous users we created:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Enable%20remote%20desktop.png">
      <img src="https://img.shields.io/badge/-Enable%20remote%20desktop-0000FF?style=for-the-badge" />
    </a>


- Lets use our crowbar tool now to brute force tsmith user with our list of passwords in our passwords.txt file:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Use%20crowbar%20to%20bruteforce%20tsmith%20user%20with%20password.txt%20file.png">
      <img src="https://img.shields.io/badge/-Use%20crowbar%20to%20bruteforce%20tsmith%20user%20with%20password.txt%20file-0000FF?style=for-the-badge" />
    </a>


- After we done the attack lets head over to our Splunk and check out our attack performed:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Analyzing%20our%20tsmith%20attack%20on%20Splunk.png">
      <img src="https://img.shields.io/badge/-Analyzing%20our%20tsmith%20attack%20on%20Splunk-0000FF?style=for-the-badge" />
    </a>


## Implementing Atomic Red Team Tactics

- We will downloa atomic red team in the command promt on our target machine:

    <a href="https://github.com/FrancisDunne/Active_Directory/blob/main/Install%20Atomic%20Red%20Team.png">
      <img src="https://img.shields.io/badge/-Install%20Atomic%20Red%20Team-0000FF?style=for-the-badge" />
    </a>


























