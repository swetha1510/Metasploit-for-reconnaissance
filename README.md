# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:


## OUTPUT:
![eh exp 51](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/df8a344e-f2d7-4335-8ae0-65c9a31fa53f)

Invoke msfconsole:
![eh exp 52](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/19a1a44e-ebe1-45d7-abff-35eb999b4108)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![eh exp 53](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/024b235a-4ea0-4ade-83f9-3a95d57079e2)
Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
OUTPUT:
![eh exp 54](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/e0178265-4fee-499f-be58-5d312a73b661)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
OUTPUT:
![eh exp 55](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/6b7d0f40-5ffb-4877-ab5a-fbb89f2a6a45)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

OUTPUT:
![eh exp 56](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/8f4f249b-17dd-4676-bf42-ee767f437290)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,
OUTPUT
![eh exp 57](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/d3be638d-46f6-4634-b9b8-5f2586cb1fd2)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![eh exp 58](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/2ea9e90c-3c66-4cd3-b05f-2c98c5d54ef0)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![eh exp 59](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/d0c3c6dd-bfc8-4dee-a110-8f3fd9fc59be)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![eh exp 510](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/47134c49-ed52-4e29-b06a-b7574728f7e7)
Use the set rhosts command to set the parameter and run the module, as follows:
![eh exp 511](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/5cbb4ec7-45e2-42cd-b868-216ed6682e73)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![eh exp 512](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/9f31c51a-f5a0-46c6-aef6-bdc03dea8efb)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![eh exp 513](https://github.com/swetha1510/Metasploit-for-reconnaissance/assets/120623583/d2882103-f06a-49c8-9c71-a6f4f7685a93)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
