All devices have NO pre-configurations:

1. Configure the PCs and routers according to the network diagram (hostnames, IP addresses, etc.)
    Remember to configure the gateway on the PCs.
    (You don't have to configure the switches)

    Answer:
    1. Click PC1 > Config
    2. In Default Gateway text input, type: 192.168.1.254
    3. Click FastEthernet0
    4. In IPv4 Address text input, type: 192.168.1.1
    5. Do the same with PC2
    6. Click R1 > CLI
    7. Type: en
    8. Type: conf t
    9. Type: host R1
    10. Type: int g0/1
    11. Type: ip ad 192.168.1.254 255.255.255.0
    12. Type: desc ## to SW1 ##
    13. Type: no shut
    14. Type: do sh ip int br
    15. Do the same with g0/0
    16. Do the same with R2 & R3
---
2. Configure static routes on the routers to enable PC1 to successfully ping PC2.

    Answer:
    1. Click R1 > CLI
    2. In global config mode, type: ip route 192.168.3.0 255.255.255.0 192.168.12.2
    3. Type: do sh ip ro
    4. Click R2 > CLI
    5. In global config mode, type: ip route 192.168.1.0 255.255.255.0 g0/0
    6. Type: ip route 192.168.3.0 255.255.255.0 192.168.13.3
    7. Type: do sh ip ro
    8. Click R3 > CLI
    9. In global config mode, type: ip route 192.168.1.0 255.255.255.0 192.168.13.2
    10. Type: do sh ip ro
    1. Click PC1 > Desktop > Command Prompt
    12. Type: ping 192.168.3.1  
    Note: first ping might fail due to ARP
