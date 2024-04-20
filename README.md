# EXP-4.Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software :
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer.All commands related to Network configuration which includes how to switch to privilege modeand normal mode and how to configure router interface and how to save this configuration toflash memory or permanent memory.
This commands includes:

1.Configuring the Router commands

2.General Commands to configure network

3.Privileged Mode commands of a router 

4.Router Processes & Statistics

5.IP Commands

6.Other IP Commands e.g. show ip route etc.


## PROGRAM:
## PING COMMAND
### CLIENT
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

## TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
## PING COMMAND
### CLIENT
![image](https://github.com/Safeeq-Fazil/4.Execution_of_NetworkCommends/assets/118680361/94b257b7-bc90-4764-a87c-ab7fae09e288)

### SERVER
![image](https://github.com/Safeeq-Fazil/4.Execution_of_NetworkCommends/assets/118680361/699ce24a-a2c9-4f94-a7b5-9fd7ecb6f981)

## TRACEROUTE COMMAND
![image](https://github.com/Safeeq-Fazil/4.Execution_of_NetworkCommends/assets/118680361/e6700ae2-fe8f-4c02-b36c-a6e01786ff2a)

## Result
Thus Execution of Network commands Performed successfully.
