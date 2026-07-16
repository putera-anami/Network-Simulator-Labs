1. Configure the switchports connecting switches as trunk ports.
   Disable DTP on the ports.
   Confirm the administrative and operational mode of each interface.

   Answer:
   1. SW1:
      - Type: en
      - Type: conf t
      - Type: in g0/1
      - Type: do sh in g0/1 sw
      - Type: sw m t
      - Type: do sh in g0/1 sw
      - Type: switchport nonegotiate
      - Type: do sh in g0/1 sw
   2. SW2:
      - Type: en
      - Type: conf t
      - Type: in r g0/1 - 2
      - Type: sw m t
      - Type: sw n
      - Type: do sh in g0/1 sw
      - Type: do sh in g0/2 sw
   3. SW3:
      - Type: en
      - Type: conf t
      - Type: in g0/1
      - Type: sw m t
      - Type: sw n
      - Type: do sh in g0/1 sw

---
2. Configure SW1 in VTP domain CCNA.
   Create VLANs 10, 20, and 30 on SW1.
   Have SW2 and SW3 added VLANs 10, 20, and 30?

   Answer:
   1. SW1:
      - Type: exit
      - Type: do sh vtp status
      - Type: vtp domain CCNA
      - Type: vlan 10
      - Type: vlan 20
      - Type: vlan 30
      - Type: exit
      - Type: do sh vtp s
   2. SW2:
      - Type: exit
      - Type: do sh vtp s
      - Type: do sh vl br
   3. SW3:
      - Type: exit
      - Type: do sh vtp s
      - Type: do sh vl br
---
3. Configure SW2 in VTP transparent mode.
   Add VLAN40 to SW2.
   Is VLAN40 added to the VLAN database of SW1/SW3?

   Answer:
   1. SW2:
      - Type: vtp mode transparent
      - Type: vlan 40
      - Type: exit
      - Type: do sh vtp s
   2. SW1:
      - Type: do sh vl br
   3. SW3:
      - Type: do sh vl br
---
4. Configure SW3 in VTP client mode.
   Try to configure VLAN50 on SW3. Is it added?

   Answer:
   1. SW3:
      - Type: vtp mode client
      - Type: vlan 50
         *VTP VLAN configuration not allowed when device is in CLIENT mode.
---
5. Configure all switchports connected to hosts in the correct VLAN.
   Manually configure them as access ports.
   Is DTP still enabled on the switchports?

   Answer:
   1. SW3:
      - Type: in f0/1
      - Type: do sh in f0/1 sw
      - Type: sw mode ac
      - Type: sw ac vlan 10
      - Type: do sh in f0/1 sw
      - Type: in r f0/2 - 3
      - Type: sw m a
      - Type: sw a v 30
      - Type: in f0/4
      - Type: sw m a
      - Type: sw a v 20
   2. SW2:
      - Type: in r f0/1 - 2
      - Type: sw m a
      - Type: sw a v 40
   3. SW1:
      - Type: in r f0/1 - 2
      - Type: sw m a
      - Type: sw a v 10
      - Type: in f0/3
      - Type: sw m a
      - Type: sw a v 20