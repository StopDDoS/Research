## protocol discerning features:
- spread/(shannon) entropy (sum of differences)
- XML_LIKE ">" "<" characters etc
- ASCII_LIKE >A <z / average around base
- SRCPORT?
- pkt_len entropy
- NULL_BYTE_COUNT
- probably different for the first packet and later packets due to encryption setup

Use AVX-512 to check 64-bytes at once for the sum of differences and counting for XMLLIKE and ASCIILIKE

for pkt_len entropy
