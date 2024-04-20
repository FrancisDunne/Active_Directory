# Active Directory Project

## Objective

The Active Directory project aimed to design and implement a robust directory service infrastructure to manage and centralize network resources efficiently. The primary focus was to establish secure user authentication, authorization, and access control mechanisms, enhancing overall network security and administrative efficiency.

### Skills Learned

- Proficiency in designing and deploying Active Directory environments.
- Understanding of user and group management in Active Directory.
- Implementation of Group Policy Objects (GPOs) for centralized configuration management.
- Integration of Active Directory with other services and applications.
- Troubleshooting and maintenance of Active Directory infrastructure.

### Tools Used

- Active Directory Domain Services (AD DS) for directory service implementation.
- Group Policy Management Console (GPMC) for centralized policy management.
- Active Directory Users and Computers (ADUC) for user and group administration.
- DNS and DHCP services for network infrastructure support.

## Steps

### Ref 1: Network Diagram

<a href="https://github.com/FrancisDunne/Active_Directory/files/15049021/Diagram.pdf">Diagram.pdf</a>


This network diagram illustrates the topology of the Active Directory environment, showcasing the placement of domain controllers, organizational units (OUs), and client machines. It provides an overview of the network infrastructure supporting the Active Directory deployment.

### Ref 2: Active Directory Users and Groups

[Insert screenshot of Active Directory Users and Computers]

This screenshot displays the Active Directory Users and Computers management console. It showcases the organization's user accounts, group memberships, and organizational unit (OU) structure within the Active Directory domain.

### Ref 3: Group Policy Objects (GPOs)

[Insert screenshot of Group Policy Management Console]

This screenshot showcases the Group Policy Management Console (GPMC), where Group Policy Objects (GPOs) are configured. It demonstrates the policies applied to various OUs within the Active Directory domain, including settings related to security, software deployment, and system configuration.

### Ref 4: Active Directory Integration

[Insert screenshot of Active Directory integration]

This screenshot demonstrates the integration of Active Directory with other services and applications, such as Microsoft Exchange Server or third-party authentication systems. It highlights the configuration settings and options involved in integrating Active Directory for centralized user authentication and authorization.

### Ref 5: DNS and DHCP Configuration

[Insert screenshot of DNS and DHCP management]

This screenshot showcases the configuration of DNS and DHCP services within the Active Directory environment. It includes settings related to DNS zone configuration, DHCP scope management, and DNS dynamic updates to support Active Directory domain services.

### Ref 6: Active Directory Replication

[Insert screenshot of Active Directory replication]

This screenshot illustrates the Active Directory Sites and Services management console, focusing on replication settings and site topology configuration. It demonstrates the replication schedule, replication partners, and site link configuration to ensure efficient replication of directory information across distributed domain controllers.





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
