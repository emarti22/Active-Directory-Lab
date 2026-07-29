# Active-Directory-Lab
Active Directory home lab demonstrating Windows Server administration, user management, DNS, DHCP, and Group Policy.
# Details and screenshots
## Domain Controller DC01 and its services:
![DC01.1](screenshots/DC-and-services1.png)

![DC01.2](screenshots/DC-and-services2.png)

The services that DC01 is running include Active Directory, DHCP, DNS, and Remote Access and this project uses all of these.

### DHCP was configured on DC01 to automatically assign IP addresses to domain clients. CLIENT1 successfully received an address within the configured scope.

![DHCP Scope and Lease](screenshots/DHCP-scopeLease.PNG)

![Client IP Config](screenshots/Client-ipconfig.PNG)

## The DNS records reflect that everything is working

![DNS Records](screenshots/DNS-records.PNG)

## 1000 Users were added to the domain using PowerShell including CLIENT01's current user emartin.

![Users](screenshots/Users.PNG)

## Promoting _ADMINS OU (which contains a second Evan Martin user) to gain admin privileges using a GPO

![Elevating _ADMINS OU](screenshots/elevate-ADMINS-OU.PNG)

![_ADMINS are now Member Of Administrators](screenshots/gpo-local-admin-membership.png)

## The following two screenshots show the privilege elevation in action

![Attempting to make an administrative change with a-emartin](screenshots/client-admin-verification1.png)

## Attempting to open the client's network adapter properties requires elevated access, let's see if a-emartin is able to get through. 

![Success!](screenshots/client-admin-verification2.png)

## The login worked, a-emartin was able to sign in.

## And if we attempt to sign in as aabrev, a member of the _USERS group:

![aabrev-attempt1](screenshots/aabrev-attempt1.PNG)

![aabrev-attempt1](screenshots/aabrev-attempt2.PNG)

## The attempt fails, and as shown in the second image this is because aabrev is not a member of _ADMINS, therefore permissions work as intended.

# It seems I messed up the GPO and I need to redo this part. Added another user to _ADMINS and they did not get privileges. Change to enforcing a Wallpaper for _USERS.
