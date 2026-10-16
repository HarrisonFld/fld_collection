# Horse Plinko Cyber Challenge 4 (Windows Server 2022)
* Does not have winget. Install and use [Chocolatey](https://chocolatey.org/install#individual) instead
* Does not use Active Directory at all

## Scored Services:
* RDP
* Jenkins

## First Thing To Do After Logging In
* Change the password of jmoney (and update it in the scoreboard)
* Make new admin user with new password (MAKE SURE YOU CAN LOGIN INTO IT)
* Install choco
* Install sysinternals and needed tools (using choco)
* Make backups of critical and scored services

## During Active Defense
* Monitor OpenObserve SIEM
* Check on users, logged-in users, and user logs
    * Use task manager for monitoring logged-in users
* Block IPs of the Attackers if found

## Jenkins
1. Using ``` choco install caddy ```
2. Using caddy put cf onto the server and then run ``` caddy start --config cf ```
3. Go to ProgramData\Jenkins\jenkins.xml and change the http port to 8001
4. Then go to /restart under the Jenkins
5. To make it run without a terminal window:
    * ``` Start-Process "caddy" -ArgumentList "start" -WindowStyle Hidden ```
    * ``` caddy reload cf ``` <- At cf location

## Updating Users and Passwords
In general changing users is done under the software "Computer Management"
* Adding users, deleting users, and any user operation can be done here
    * To monitor logged-in users go to Task Manager and click on "Users" tab
* If a user needs to be added to administrator, click on properties and add user to the role "Administrators"


## Windows Firewall and Blocking IPs
