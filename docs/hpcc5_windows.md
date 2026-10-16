# Horse Plinko Cyber Challenge 5 (Windows Server 2022)
* Does not have winget. Install and use [Chocolatey](https://chocolatey.org/install#individual) instead
* Does not use Active Directory at all


## Scored Services:
* RDP
* Jenkins

## First Thing To Do After Logging In
* Install sysinternals and needed tools (using choco)
* Change the password (and maybe username) of plinktern
* Change the password of jmoney (and update it in the scoreboard)
* Make backups of critical and scored services

## During Active Defense
* Monitor OpenObserve SIEM
* Check on users, logged-in users, and user logs
* Block IPs of the Attackers if found

## Jenkins
1. Using ``` choco install caddy ```
2. Using caddy put cf onto the server and then run ``` caddy start --config cf ```
3. Go to ProgramData\Jenkins\jenkins.xml and change the http port to 8001
4. Then go to /restart under the Jenkins
5. To make it run without a terminal window:
    * ``` Start-Process "caddy" -ArgumentList "start" -WindowStyle Hidden ```
    * ``` caddy reload cf ``` <- At cf location
