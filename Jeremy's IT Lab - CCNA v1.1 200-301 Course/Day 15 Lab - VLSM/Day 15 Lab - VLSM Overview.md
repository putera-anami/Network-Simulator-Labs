Subnet the 192.168.5.0/24 network to provide sufficient addressing for each LAN.
(Also, the point-to-point connection between R1 and R2).

    Answer:
    1. LAN2 (64 hosts): /25
        - network address: 192.168.5.0
        - usable address: 192.168.5.1 - 192.168.5.126 (126 address)
        - broadcast address: 192.168.5.127
    2. LAN1 (45 hosts): /26
        - network address: 192.168.5.128
        - usable address: 192.168.5.129 - 192.168.5.190 (62 address)
        - broadcast address: 192.168.5.191
    3. LAN3 (14 hosts): /28
        - network address: 192.168.5.192
        - usable address: 192.168.5.193 - 192.168.5.206 (14 address)
        - broadcast address: 192.168.5.207
    4. LAN4 (9 hosts): /28
        - network address: 192.168.5.208
        - usable address: 192.168.5.209 - 192.168.5.222 (14 address)
        - broadcast address: 192.168.5.223
    5. Point-to-Point: /30 or /31. We use /30 in this lab
        - network address: 192.168.5.224
        - usable address: 192.168.5.225 - 192.168.5.226 (2 address)
        - broadcast address: 192.168.5.227

---
Assign the first usable address to the PC in each LAN.

    Answer:
    1. PC2:
        - Click PC2 > Config
        - In Default Gateway text input, type: 192.168.5.126
        - Click FastEthernet0
        - In IPv4 Address text input, type: 192.168.5.1
        - Press tab or enter, subnet mask will filled with 255.255.255.0
        - In subnet mask input, change it to: 255.255.255.128
    2. PC1:
        - Click PC1 > Config
        - In Default Gateway text input, type: 192.168.5.190
        - Click FastEthernet0
        - In IPv4 Address text input, type: 192.168.5.129
        - In subnet mask input, change it to: 255.255.255.192
    3. PC3:
        - Click PC3 > Config
        - In Default Gateway text input, type: 192.158.5.206
        - Click FastEthernet0
        - In IPv4 Address text input, type: 192.168.5.193
        - In subnet mask input, change it to: 255.255.255.240
    4. PC4:
        - Click PC4 > Config
        - In Default Gateway text input, type: 192.158.5.222
        - Click FastEthernet0
        - In IPv4 Address text input, type: 192.168.5.209
        - In subnet mask input, change it to: 255.255.255.240

---
Assign the last usable address to the router's interface in each LAN.

    Answer:
    1. R1 g0/1:
        - Type: en
        - Type: conf t
        - Type: int g0/1
        - Type: ip ad 192.168.5.126 255.255.255.128
        - Type: no shut
        - Type: do sh ip int g0/1
    2. R1 g0/0:
        - Type: int g0/0
        - Type: ip ad 192.168.5.190 255.255.255.192
        - Type: no shut
        - Type: do sh ip int g0/0
    3. R2 g0/0:
        - Type: en
        - Type: conf t
        - Type: int g0/0
        - Type: ip ad 192.168.5.206 255.255.255.240
        - Type: no shut
        - Type: do sh ip int g0/0
    3. R2 g0/1:
        - Type: int g0/1
        - Type: ip ad 192.168.5.222 255.255.255.240
        - Type: no shut
        - Type: do sh ip int g0/1
    4. R1 g0/0/0:
        - Type: int g0/0/0
        - Type: ip ad 192.168.5.225 255.255.255.252
        - Type: no shut
        - Type: do sh ip int g0/0/0
    5. R2 g0/0/0:
        - Type: int g0/0/0
        - Type: ip ad 192.168.5.226 255.255.255.252
        - Type: no shut
        - Type: do sh ip int g0/0/0
---
Configure static routes on each router so that all PCs can ping eachother.

    Answer:
    1. R2:
        - In global config mode, type: ip route 192.168.5.128 255.255.255.192 192.168.5.225
        - Type: ip route 192.168.5.0 255.255.255.128 192.168.5.225
        - Type: do sh ip route
    2. R1:
        - In global config mode, type: ip route 192.168.5.192 255.255.255.240 192.168.5.226
        - Type: ip route 192.168.5.208 255.255.255.240 192.168.5.226