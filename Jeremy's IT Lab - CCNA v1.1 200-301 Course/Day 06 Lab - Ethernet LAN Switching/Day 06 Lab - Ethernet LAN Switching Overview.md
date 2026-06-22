Both switches have an empty MAC address table, and all PCs have an empty ARP table.

1. If PC1 pings to PC3, what messages will be sent over the network, 
     and which devices will receive them?
Answer:
1. ARP Request (received by PC2, PC3, PC4)
2. ARP Reply (received by PC1)
3. ICMP Echo Request (received by PC3)
4. ICMP Echo Reply (received by PC1)

2. Send the ping and use Packet Tracer's 'simulation mode' to verify your answer.
Answer:
1. Click Simulation in the bottom right
2. Click PC1 > Desktop > Command Prompt
3. Type: ping 192.168.1.3

3. Use pings to generate network traffic and allow the switches to learn the MAC addresses 
     of all PCs on the network.
Answer:
1. Click PC2 > Desktop > Command Prompt
2. Type: ping 192.168.1.4

4. Use 'show' commands on the switches to identify the MAC address of each PC.
Answer:
1. Click SW1 or SW2 > CLI
2. Type: show mac ad

5. Clear the dynamic MAC addresses from the MAC address table of each switch.
Answer:
1. Type: clear mac address-table dynamic