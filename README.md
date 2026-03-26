# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## program
~~~
Server.py
import socket
from pythonping import ping
s = socket.socket()
# Bind to localhost and port
s.bind(('localhost', 8000))
# Listen for connections
s.listen(5)
print("Ping Server started... Waiting for connection")
# Accept connection
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    if not hostname:
        break
    try:
        result = ping(hostname, count=4, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Host Not Found".encode())
c.close()

Client.py
import socket
# Create socket
s = socket.socket()
# Connect to server
s.connect(('localhost', 8000))
while True:
    website = input("Enter the website you want to ping: ")
    if website.lower() == "exit":
        break
    s.send(website.encode())
    result = s.recv(1024).decode()
    print("\nPing Result:\n", result)
s.close()

Traceroute.py
import os
print("Running Traceroute...\n")
os.system("C:\\Windows\\System32\\tracert.exe google.com")

~~~
## Output

1)ping

<img width="844" height="353" alt="image" src="https://github.com/user-attachments/assets/3b5f7b70-f68f-4030-be37-b9cf692dd7bf" />

2)Tracert

<img width="1046" height="561" alt="image" src="https://github.com/user-attachments/assets/a1872a9d-5eda-4661-94cf-81c126ca6827" />

3)ipconfig

<img width="984" height="719" alt="image" src="https://github.com/user-attachments/assets/f8d8e043-28b2-405c-be6a-d4c56f83859a" />

4)netstat

<img width="886" height="909" alt="image" src="https://github.com/user-attachments/assets/d9116627-e9e7-416f-83f0-9a4701b4ecb7" />

5)nslookup

<img width="799" height="555" alt="image" src="https://github.com/user-attachments/assets/30afdd18-2805-4e7f-b99d-b7adf2a7536f" />

6)getmac
<img width="956" height="171" alt="image" src="https://github.com/user-attachments/assets/36578b2e-44c0-47eb-87f6-648679cb8a93" />

7)nbtstat

<img width="1105" height="600" alt="image" src="https://github.com/user-attachments/assets/585351e8-c2ec-4ce9-bc1c-9481072e956f" />

8)arp

<img width="958" height="789" alt="image" src="https://github.com/user-attachments/assets/226883ff-2025-49eb-b25a-0740cccaa9a6" />

9)systeminfo

<img width="705" height="964" alt="image" src="https://github.com/user-attachments/assets/c862046a-d70f-4700-9cb5-002f3b558751" />

## Result
Thus Execution of Network commands Performed 
