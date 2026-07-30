# Active-Directory-Lab
Active Directory home lab demonstrating Windows Server administration, user management, DNS, DHCP, and Group Policy.
# Goals
### Set up a domain controller with Active Directory, DHCP, and DNS.
### Disable the control panel and command prompt on client machines logged in as one of 1000 users in an Organizational Group called _USERS using Group Policy. 

# Details and screenshots
### Domain Controller DC01 and its services:
![DC01.1](screenshots/DC-and-services1.png)

![DC01.2](screenshots/DC-and-services2.png)

The services that DC01 is running include Active Directory, DHCP, and DNS.

### DHCP was configured on DC01 to automatically assign IP addresses to domain clients. CLIENT1 successfully received an address within the configured scope:

![DHCP Scope and Lease](screenshots/DHCP-scopeLease.PNG)

![Client IP Config](screenshots/Client-ipconfig.PNG)

### The DNS records show DC01 and CLIENT1 in lookup zones:

![DNS Records](screenshots/DNS-records.PNG)

### DNS is able to resolve both DC01 and CLIENT1's request to ping each other, so we know it is working:

![DNS client>dc](screenshots/DNS-records2.PNG)

![DNS dc>client](screenshots/DNS-records3.PNG)

The firewall rule "File and Printer Sharing (Echo Request)" was disabled for Domains preventing DC01 sending packets to CLIENT1. However, after enabling this rule on CLIENT1 the packets sent successfully.

### The Organizational Units _ADMINS, _USERS, and Domain Controllers were created and 1000 Users were added to the _USERS group using a PowerShell script and a text file with 1000 random names.

![Users](screenshots/Users.PNG)

### Implementing the first Group Policy which needs to disable the control panel for members of the _USERS OU.

![GPO1](screenshots/GPO-1.PNG)

![GPO2](screenshots/GPO-2.PNG)

![GPO3](screenshots/GPO-3.PNG)

![GPO-success1](screenshots/GPO-success1.PNG)

![GPO-success2](screenshots/GPO-success2.PNG)
