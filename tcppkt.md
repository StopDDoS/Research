# todo

Just sending a lot of packets, can often be stopped by using SYN cookies / SYN Proxy. But that requires a stateful system which is often way heavier than a stateless solution. Nevertheless with modern hardware this is starting to become less of a problem. Even the linux iptables system has a builtin syn proxy module.



SYN flood:

![synspoof](https://www.cloudflare.com/img/learning/ddos/what-is-a-ddos-attack/syn-flood-ddos-attack.png)

SYN proxy:

![syn proxy](https://www.cisco.com/web/about/ac123/ac147/images/ipj/ipj_9-4/94_syn_fig6_lg.jpg)