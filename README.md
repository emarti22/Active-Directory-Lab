## Active-Directory-Lab
Active Directory home lab demonstrating Windows Server administration, user management, DNS, DHCP, and Group Policy.
## Details and screenshots
#Domain Controller DC01 and its services:
![DC01.1](screenshots/DC-and-services1)

![DC01.2](screenshots/DC-and-services2)

The services that DC01 is running include Active Directory, DHCP, DNS, and Remote Access and this project uses all of these.

#DHCP was configured on DC01 to automatically assign IP addresses to domain clients. CLIENT1 successfully received an address within the configured scope.

![DHCP Scope and Lease](screenshots/DHCP-scopeLease.PNG)

![Client IP Configuration](screenshots/Client-ipconfig.PNG)
