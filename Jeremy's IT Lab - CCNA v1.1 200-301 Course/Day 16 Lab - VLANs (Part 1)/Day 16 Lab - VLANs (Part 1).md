1. Configure the correct IP address/subnet mask on each PC.
    Set the gateway address as the LAST USABLE address of the subnet.

    Answer:
    1. PC1:
        - Click PC1 > Config
        - In Default Gateway text input, type: 10.0.0.62
        - Click FastEthernet0
        - In IPv4 Address text input, type: 10.0.0.1
        - In subnet mask input, change it to: 255.255.255.192
    2. PC2:
        - Click PC2 > Config
        - In Default Gateway text input, type: 10.0.0.62
        - Click FastEthernet0
        - In IPv4 Address text input, type: 10.0.0.2
        - In subnet mask input, change it to: 255.255.255.192
    3. PC3:
        - Click PC3 > Config
        - In Default Gateway text input, type: 10.0.0.126
        - Click FastEthernet0
        - In IPv4 Address text input, type: 10.0.0.65
        - In subnet mask input, change it to: 255.255.255.192
    4. PC4:
        - Click PC4 > Config
        - In Default Gateway text input, type: 10.0.0.126
        - Click FastEthernet0
        - In IPv4 Address text input, type: 10.0.0.66
        - In subnet mask input, change it to: 255.255.255.192
    5. PC5:
        - Click PC5 > Config
        - In Default Gateway text input, type: 10.0.0.190
        - Click FastEthernet0
        - In IPv4 Address text input, type: 10.0.0.129
        - In subnet mask input, change it to: 255.255.255.192
    6. PC6:
        - Click PC6 > Config
        - In Default Gateway text input, type: 10.0.0.190
        - Click FastEthernet0
        - In IPv4 Address text input, type: 10.0.0.130
        - In subnet mask input, change it to: 255.255.255.192
---
2. Make three connections between R1 and SW1.
    Configure one interface on R1 for each VLAN.
    Make sure the IP addresses are the gateway address you configured on the PCs.

    Answer:
    1. Make 3 connections with straight through cable between R1 and SW1. Adjust the interface based on the labels
    2. R1:
        - Type: en
        - Type: conf t
        - Type: int g0/0
        - Type: ip ad 10.0.0.62 255.255.255.192
        - Type: no shut
        - Type: int g0/1
        - Type: ip ad 10.0.0.126 255.255.255.192
        - Type: no shut
        - Type: int g0/2
        - Type: ip ad 10.0.0.190 255.255.255.192
        - Type: no shut
        - Type: do sh ip int br
---
3. Configure SW1's interfaces in the proper VLANs.
    Remember the interfaces that connect to R1!
    Name the VLANs
     (Engeering, HR, Sales)

    Answer:
    SW1:
        - Type: en
        - Type: conf t
        - Type: int r g0/1, f3/1, f4/1
        - Type: switchport mode access
        - Type: switchport access vlan 10
        - Type: int r g1/1, f5/1, f6/1
        - Type: sw mode ac
        - Type: sw ac vlan 20
        - Type: int r g2/1, f7/1, f8/1
        - Type: sw mode ac
        - Type: sw ac vlan 30
        - Type: do sh vl br
        - Type: vlan 10
        - Type: name ENGINEERING
        - Type: vlan 20
        - Type: name HR
        - Type: vlan 30
        - Type: name SALES
        - Type: do sh vl br
---
4. Ping between the PCs to check connectivity.
    Send a broadcast ping from a PC (ping the subnet broadcast address),
     and see which PCs devices receive the broadcast
      (use Packet Tracer's 'Simulation Mode')

    Answer:
    1. Click PC1 > Desktop > Command Prompt
    2. Type: ping 10.0.0.65
    3. Type: ping 10.0.0.63