All devices are preconfigured from the end of Day 17's lab (SW2 has been replaced with a multilayer switch):
Hosts are in the correct VLANs.
SW1-SW2 are connected via trunk.
R1-SW2 are connected via ROAS.

1. Replace the ROAS configuration on R1-SW2 with a point-to-point Layer 3 connection.
    Use the IP addresses given in the network diagram.
    Configure a default route on SW2, with R1's G0/0 interface as the next hop.

    Answer:
    1. R1:
        - Type: en
        - Type: sh run
        - Type: sh ip in br
        - Type: conf t
        - Type: no g0/0.10
        - Type: no g0/0.20
        - Type: no g0/0.30
        - Type: do sh run
        - Type: do sh ip in br
        - Type: in g0/0
        - Type: ip ad 10.0.0.194 255.255.255.252
    2. SW2:
        - Type: en
        - Type: sh run
        - Type: conf t
        - Type: default int g1/0/2
        - Type: do sh run
        - Type: in g1/0/2
        - Type: ip ?
        - Type: no switchport
        - Type: ip ?
        - Type: ip ad 10.0.0.193 255.255.255.252
        - Type: exit
        - Type: do sh ip ro
        - Type: ip routing
        - Type: do sh ip ro
        - Type: ip route 0.0.0.0 0.0.0.0 10.0.0.194
        - Type: do sh ip ro
---
2. Configure SVIs on SW2, one for each VLAN.
     Assign the last usable IP address of each subnet to the appropriate SVI.

    Answer:
    1. SW2:
        - Type: do sh vl br
        - Type: int vlan 10
        - Type: ip ad 10.0.0.62 255.255.255.192
        - Type: int vl 20
        - Type: ip ad 10.0.0.126 255.255.255.192
        - Type: int vl 30
        - Type: ip ad 10.0.0.190 255.255.255.192
        - Type: exit
        - Type: do sh ip int br
---
3. Test inter-VLAN connectivity by pinging between VLANs.

    Answer:
    1. Click PC7 > Desktop > Command Prompt
    2. Type: ping 10.0.0.129
---
4. Test connectivity to the Internet by pinging 1.1.1.1
    (Routes have already been configured on R1 and the Internet router)

    Answer:
    1. In any PC > Desktop > Command Prompt
    2. Type: ping 1.1.1.1