PC1 and PC2 are unable to ping eachother.

There is one misconfiguration on each router.

Find and fix the misconfigurations.

You have successfully completed the lab when PC1 and PC2 can ping eachother.

    Answer:
    1. Click PC1 > Desktop > Command Prompt > ping PC3
    Note: request timed out
    2. ping default gateway
    Note: replied
    3. Click R1 > CLI
    4. Type: en
    5. Type: sh ip int br
    Note: no misconfiguration
    6. Type: sh ip ro
    Note: next hop misconfiguration
    7. Type: sh r | include ip route
    8. Left click and block the line
    9. Right click and copy the line
    10. Type: conf t
    12. Right click and paste the line
    13. Ctrl + A to go to the beginning of the line
    14. Type: no 
    Note: after no with space, make sure the line is "no ip route 192.168.3.0 255.255.255.0 192.168.12.3"
    15. Type: do sh r | i ip ro
    16. Paste the previous configuration, change 3 with 2
    17. With arrow key choose "do sh r | i ip ro"
    18. Click R2 > CLI
    19. Type: en
    20. Type: sh ip int br
    Note: no misconfig
    21. Type: sh ip ro
    Note: next hop misconfig
    22. Type: conf t
    23. Type: ip route 192.168.3.0 255.255.255.0 g0/1
    24. Type: do sh ip ro
    Note: latest config doesn't override the misconfig one. The router will load-balance over the 2 routes. Sending some packets out of g0/0, and some packets out of g0/1. Since g0/0 int is wrong, let's remove the config
    25. Type: do sh r | i ip ro
    26. Copy the wrong config line, and paste it
    27. Type: "no " in front of the wrong config line
    28. Type: do sh ip ro
    29. Click R3 > CLI
    30. Type: en
    31. Type: sh ip int br
    Note: ip address misconfig
    32. Type: conf t
    33. Type: int g0/0
    34. Type: do sh run
    35. Type: ip ad 192.168.13.3 255.255.255.0
    36. Type: do sh run
    Note: fixed
    37. Type: do sh ip ro
    Note: no misconfig
    38. ping PC1 to PC2
