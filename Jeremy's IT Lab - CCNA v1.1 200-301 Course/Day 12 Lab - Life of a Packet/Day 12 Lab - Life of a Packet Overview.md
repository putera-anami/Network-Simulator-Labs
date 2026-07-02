1. PC1 pings PC4.  
Identify the src/dst MAC address at each specified point in the route to PC4.
Identify the MAC address by the device and interface (ie. the MAC of R1 G0/0)
A. Source/Destination MAC at PC1 → SW1 segment
B. Source/Destination MAC at SW1 → R1 segment
C. Source/Destination MAC at R1 → R2 segment
D. Source/Destination MAC at R2 → R3 segment
E. Source/Destination MAC at R3 → SW2 segment
F. Source/Destination MAC at SW2 → PC4 segment

Use the CLI and Packet Tracer's simulation mode to verify your answers.
(Before you enter simulation mode, ping once to complete ARP/the MAC learning process.)

    Answer:
    A. src: PC1 MAC address, dst: R1 G0/0 MAC address
    B. src: PC1 MAC address, dst: R1 G0/0 MAC address
    C. src: R1 G0/1 MAC address, dst: R2 G0/0 MAC address
    D. src: R2 G0/1 MAC address, dst: R3 G0/0 MAC address
    E. src: R3 G0/1 MAC address, dst: PC4 MAC address
    F. src: R3 G0/1 MAC address, dst: PC4 MAC address
---
2. PC1 pings PC3.
Identify the src/dst MAC address at each specified point in the route to PC3.
Identify the MAC address by the device and interface (ie. the MAC of R1 G0/0)
A. Source/Destination MAC at PC1 → SW1
B. Source/Destination MAC at SW1 → PC3

Use the CLI and Packet Tracer's simulation mode to verify your answers.
(Before you enter simulation mode, ping once to complete ARP/the MAC learning process.)

    Answer:
    A. src: PC1 MAC address, dst: PC3 MAC address
    B. src: PC1 MAC address, dst: PC3 MAC address
---
3. PC4 pings PC1.
Identify the src/dst MAC address at each specified point in the route to PC1.
Identify the MAC address by the device and interface (ie. the MAC of R1 G0/0).

WRITE YOUR ANSWERS IN THE COMMENT SECTION OF THE VIDEO :)

    Answer:
    A. PC4 → SW2 | src: PC4 MAC address, dst: R3 G0/1 MAC address
    B. SW2 → R3 | src: PC4 MAC address, dst: R3 G0/1 MAC address
    C. R3 → R2 | src: R3 G0/0 MAC address, dst: R2 G0/1 MAC address
    D. R2 → R1 | src: R2 G0/0 MAC address, dst: R1 G0/1 MAC address
    E. R1 → SW1 | src: G0/0 MAC address, dst: PC1 MAC address
    F. SW1 → PC1 | src: G0/0 MAC address, dst: PC1 MAC address