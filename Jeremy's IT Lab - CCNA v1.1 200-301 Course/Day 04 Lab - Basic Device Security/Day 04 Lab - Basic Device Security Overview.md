1. Change the hostnames of the router and switch to the appropriate names (R1, SW1)
     ##Use the 'hostname' command in global configuration mode##

     Answer:
     1. Click R1 > CLI
     2. Type: enable
     3. Type: configure terminal
     4. Type: hostname R1
     5. Do the same with SW1
---
2.  Configure an unencrypted enable password of 'CCNA' on both devices

     Answer:
     1. In global config mode, type: enable password CCNA
---
3. Exit back to user EXEC mode and test the password

     Answer:
     1. Type: exit
     2. Do it twice
     3. Type: en
     4. Type: CCNA
---
4.  View the password in the running configuration

     Answer:
     1. Type: show running-config
---
5. Ensure that the current password, and all future passwords, are encrypted

     Answer:
     1. Type: conf t
     2. Type: service password-encryption
---
6. View the password in the running configuration

     Answer:
     1. In global config mode, type: do sh run
     2. Or if you're in privileged exec mode, type: sh run
---
7. Configure a more secure, encrypted enable password of 'Cisco' on both devices

     Answer:
     1. In global config mode, type: enable secret Cisco
---
8. Exit back to user EXEC mode and then return to privileged EXEC mode.
    Which password do you have to use?

     Answer:
     1. Type: exit
     2. Do it twice
     3. Type: en
     4. Type: Cisco
---
9. View the passwords in the running configuration.
     What encryption type number is used for the encrypted 'enable password'?
     What encryption type number is used for the encrypted 'enable secret'?

     Answer:
     1. Type: sh run
---
10. Save the running configuration to the startup configuration

     Answer:
     1. Type: write
     2. or type: write memory
     3. or type: copy running-config startup-config