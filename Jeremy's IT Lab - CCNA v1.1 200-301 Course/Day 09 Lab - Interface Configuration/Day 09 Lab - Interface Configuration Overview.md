1. Configure the hostname of R1, SW1, and SW2

    Answer:
    1. Click R1 > CLI
    2. Type: en
    3. Type: conf t
    4. Type: host R1
    5. Do all the steps with SW1 and SW2
---
2. Configure the appropriate IP addresses on R1, PC1, PC2, PC3, PC4

    Answer:
    1. On R1, type: int g0/0
    2. Type: ip ad 172.16.255.254 255.255.0.0
    3. Click PC1 > Config > FastEthernet0
    4. In IPv4 Address text input, type: 172.16.0.1
    5. Do all the steps with PC2, PC3, and PC4
---
3. Manually configure the speed and duplex on interfaces connected to other 
    networking devices (not end hosts)

    Answer:
    1. Type: speed 1000
    2. Type: duplex full  
    Note: do this on R1, SW1, and SW2
---
4. Configure appropriate descriptions on each interface

    Answer:
    1. On R1 g0/0, type: desc ## to SW1 ##
    2. On R1 g0/1 - 2, type: desc ## not in use ##
    3. On SW1 g0/1, type: ## to R1 ##
    4. On SW1 g0/2, type: ## to SW2 ##
    5. On SW1 f0/1 - 2, type: ## to end hosts ##
    6. On SW1 f0/3 - 24, type: ## not in use ##
    7. On SW2 g0/1, type: ## to SW1 ##
    8. On SW2 f0/1 - 2, type: ## to end hosts ##
    9. On SW2 g0/2, f0/3 - 24, type: ## not in use ##
---
5. Disable interfaces which are not connected to other devices

    Answer:
    1. On R1, type: no shut
    2. On SW1 f0/3 - 24, type: shut
    3. On SW2 g0/2, f0/3 - 24, type: shut
---
6. Save the configurations

    Answer:
    1. Type: wr