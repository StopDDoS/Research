# DDOS Research

## Attack types:

TCP packet attacks (SYN/ACK/SYNACK/XMAS etc.) attacks [tcppkt.md](https://github.com/NoMoreDDoS/Research/blob/Main/tcppkt.md)

TCP reflection attacks (RST, SYNACK) [tcpreflection.md](https://github.com/NoMoreDDoS/Research/blob/Main/tcpreflection.md)

UDP reflection attacks (LDAP, DNS, etc.) [udp.md](https://github.com/NoMoreDDoS/Research/blob/Main/udp.md)

## Mitigation methods
Simplest: any external scrubber service: voxtility, akamai, cloudflare, TCPShield etc

Or: In-house, based on software like wanguard or custom detection.