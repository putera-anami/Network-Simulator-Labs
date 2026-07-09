1. Configure the switch interfaces connected to PCs as access ports in the correct VLAN.

    Answer:
    1. SW1:
        - Type: en
        - Type: conf t
        - Type: in r f0/1 - 2
        - Type: sw m a
        - Type: sw a v 10
        - Type: in r f0/3 - 4
        - Type: sw m a
        - Type: sw a v 30
    2. SW2:
        - Type: en
        - Type: conf t
        - Type: in f0/1
        - Type: sw m a
        - Type: sw a v 20
        - Type: in r f0/2 - 3
        - Type: sw m a
        - Type: sw a v 10
---
2. Configure the connection between SW1 and SW2 as a trunk, allowing only the necessary VLANs.
    Configure an unused VLAN as the native VLAN.
    **Make sure all necessary VLANs exist on each switch**

    Answer:
    1. SW1:
        - Type: in g0/1
        - Type: sw m t
        - Type: sw trunk allowed v 10,30
        - Type: sw t native v 1001
        - Type: do sh vl br
    2. SW2:
        - Type: in g0/1
        - Type: sw m t
        - Type: sw t a v 10,30
        - Type: sw t n v 1001
        - Type: do sh vl br
        - Type: do sh in t
        - Type: vl 30
        - Type: exit
        - Type: do sh in t
---
3. Configure the connection between SW2 and R1 using 'router on a stick'.
     Assign the last usable address of each subnet to R1's subinterfaces.

    Answer:
    1. SW2:
        - Type: in g0/2
        - Type: sw m t
        - Type: sw t a v 10,20,30
        - Type: sw t n v 1001
    2. R1:
        - Type: en
        - Type: conf t
        - Type: in g0/0
        - Type: no sh
        - Type: in g0/0.10
        - Type: encapsulation dot1q 10
        - Type: ip ad 10.0.0.62 255.255.255.192
        - Type: in g0/0.20
        - Type: en d 20
        - Type: ip ad 10.0.0.126 255.255.255.192
        - Type: in g0/0.30
        - Type: en d 30
        - Type: ip ad 10.0.0.190 255.255.255.192
---
4. Test connectivity by pinging between PCs.  All PCs should be able to reach each other.

    Answer:
    1. Click PC7 > Desktop > Command Prompt
    2. Type: ping 10.0.0.1
    3. Type: ping 10.0.0.65
    4. Type: ping 10.0.0.129