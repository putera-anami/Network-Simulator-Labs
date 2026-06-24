1. Configure R1's hostname

    Answer:
    1. Click R1 > CLI
    2. Type: en
    3. Type: conf t
    4. Type: hostname R1
---
2. Use a 'show' command to view a list of R1's interfaces, their IP addresses, status, etc.

    Answer:
    1. In global config mode, type: do show interface brief
---
3. Configure the appropriate IP addresses on R1's interfaces, and enable the interfaces
    Configure appropriate interface descriptions

    Answer:
    1. Type: interface gigabitEthernet 0/0
    2. Type: ip address 15.255.255.254 255.0.0.0
    3. Type: description ## to SW1 ##  
    Note: ## is optional
    4. Type: no shutdown
    5. Do all the steps with int 0/1 and 0/2  
    Note: type int g0/1, ip add, desc, no shut for shortcut command
    6. Type: end  
    Note: or type exit twice to go back to priv exec mode
---
4. Use a 'show' command to verify R1's interfaces again.

    Answer:
    1. Type: sh ip int br
---
5. View the running config to confirm the configuration changes, then save the config

    Answer:
    1. Type: sh run
    2. Type: wr  
    Note: wr is shortcut for write
---
6. Configure the IP addresses of PC1, PC2, and PC3
   (Watch the video to learn how to do this in Packet Tracer)

   Answer:
   1. Click PC1 > Config > FastEthernet0
   2. In IPv4 Address text input, type: 15.0.0.1
   3. Do all the steps with PC2 and PC3
---
7. Ping from PC1 to PC2 and PC3 to test connectivity

    Answer:
    1. Click PC1 > Desktop > Command Prompt
    2. Type: ping 182.98.0.1
    3. Type: ping 201.191.20.1