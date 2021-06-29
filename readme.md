# DDOS Research

## Attack types:

TCP packet attacks (SYN/ACK/SYNACK/XMAS etc.) attacks [tcppkt.md](https://github.com/NoMoreDDoS/Research/blob/main/tcppkt.md)

TCP reflection attacks (RST, SYNACK) [tcpreflection.md](https://github.com/NoMoreDDoS/Research/blob/main/tcpreflection.md)

UDP reflection attacks (LDAP, DNS, etc.) [udp.md](https://github.com/NoMoreDDoS/Research/blob/main/udp.md)

## Mitigation methods
Simplest: any external scrubber service: voxtility, akamai, cloudflare, TCPShield etc

Or: In-house, based on software like wanguard or custom detection.

## Layers: networking jargon
![image](https://micrium.com/wp-content/uploads/2014/03/OSI-Seven-Layer-Model.png)

The most important terms are:
L2: Mac addresses, the physical address of your switch/network card/router/firewall
L3: IP protocol, ICMP: your IP addresses and some other information. May also be ICMP (often used for debugging, used in tools like ping)
L4: UDP/TCP Protocol: the raw packet bytes. TCP requires a full connection and is generally used. UDP is used when packets are allowed to be dropped and need to come as fast as quickly (video, gameservers)
L7: The actual application protocol. Think http, SIP, DNS, etc. L7 attacks are the most expensive to execute but also the most effective. Mitigation depends on the kinds of applications that you are running.


### Contributing
Has this article helped you or do you want to contribute? You are very welcome to open up a Github issue or PR request. Only together we can end this problem that is DDoS.