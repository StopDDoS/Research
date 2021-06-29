# UDP Reflection

The source IP of a UDP packet can be spoofed, thus allowing an attacker to craft a packet to for example a LDAP server, and request it to send the data to the victims IP. Effectively overloading victim's bandwidth with traffic from a legit IP. Luckily most of these ports are often not in use and can be blocked using a fast ACL.

![image](https://user-content.gitlab-static.net/6929395e0cc76f6903ea741a8a9f7283bad3753a/68747470733a2f2f626c6f672e636c6f7564666c6172652e636f6d2f636f6e74656e742f696d616765732f696c6c757374726174696f6e2d616d706c696669636174696f6e2d61747461636b2d7068332e706e67)

# common ports
```
dest == 100   // random
dest == 161   // snmp
dest == 3702  // soap over UDP random data
dest == 5353  // multicast DNS
dest == 427   // PORTMAP / SRVLOC
dest == 5060  // SIP
dest == 5683  // CoAP
dest == 520   //  RIP
dest == 500   //  ISAKMP
dest == 177   // XDMCP

source == 3283  //  ARD/ARMS (apple remote desktop & management
source == 3702  // WS-Disvoery / WS-DD  ( Web Services Dynamic Discovery (WS-Discovery)

dest == 137 
dest == 138  // NETBIOS NBDS
dest == 139 

source == 111  // PORTMAP
source == 389 /* CLDAP */ 
source == 11211 /*Memcached */ 
source == 5060 /* SIP */ 

source == 5351 /* NAT-PMP */ 
source == 19 /* CHARGEN, source or dest? */ 
source == 7 /* ECHO, source or dest? */ 
source == 17 /* QUOTD source or dest? */ 
source == 1900 /* SSDP*/ 
```

Several UDP ports used for other "bypasses":
```
source == 37810 
source == 7001 
source == 17185 
source == 3072 
source == 32414 
source == 6881 
source == 41794 
source == 2362 
source == 53413 
source == 10001
source == 502
```