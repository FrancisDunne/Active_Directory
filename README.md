# Active_Directory

An Active Directory is a database that contains users, computers, groups etc.
The server must install a service called Active Directory Domain Services (ADDS).
This service must then be promoted to a Domain Controller aka (DC).
By promoting our server to a DC, it will grant us the capability to perform
authentication using a protocol called Kerberos and also authorization for our
domain.

With ADDS we will have a database that will contain objects such as users, 
computers, groups and many more. These objects will contain attributes which
are information about the object. For example: An object user of BOB might 
contain an attribute of "First" & "Last" name.

For our virtual machine we will be using Windows 10 for our target machine,
Kali linux for the attacker machine, Windows Server 2022 for Active Directory
and Ubuntu Server 22.04 for Splunk. Everything will be hosted on VirtualBox.
