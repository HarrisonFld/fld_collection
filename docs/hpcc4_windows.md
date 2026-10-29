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

## HPCC 4 After Summary
* Placed 11 / 35 on Sunday
* Jenkins service uptime was not good (66%)

### HPCC Tips For Next Time
1. Reinstall scored services while keeping their configurations (many services came with backdoors)
    * Make sure this is possible on each service BEFORE competition
2. Turn off or remove access to boxes as soon as the competition starts
    * Red team gets access at the same time, so they in en-masse executed scripts on our machines
    * Preferably instead of turning them off allow connections only to blackbox and your machine.
3. Scripts should really be pre-made for the following:
    * Removing every user except required users (jmoney, plinktern)
    * Changing the passwords of services could be automatic (possibly, might not be realistic)
4. Downtime is ALWAYS bad 
    * Limit restarts, it adds up overtime
5. Total360 Antivirus worked
6. Look into using Yara to find malicious code
7. Make wild passwords lol
