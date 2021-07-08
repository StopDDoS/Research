# cloudflare tuning

While i am normally against using a third-party. Cloudflare has again and again showed that they are a easy and stable way to protect your website.
They have a generous free tier, but the paid tiers are absolutely also worth your money.

To start. Under attack mode is your friend. Use it if you are actively under a ddos attack at this very moment.

## Rule 1: country blocks
DDos attacks commonly happen from third-world countries or the very modern ones. I like to use the following rules for third-world countries:

Captcha:
- China
- South africa
- Continent: south america
- country: russian federation
- Country: colombia

## Threat score:
This is a real powerful one. Cloudflare assigns every request a threat score.  A higher score means that something is a higher threat.

- Off (Enterprise customers only)	N/A	Does not challenge IP addresses
- Essentially off	greater than 49	Only challenges IP addresses with the worst reputation
- Low	greater than 24	Challenges only the most threatening visitors
- Medium	greater than 14	Challenges both moderate threat visitors and the most threatening visitors
- High	greater than 0	Challenges all visitors that exhibit threatening behavior within the last 14 days
- I’m Under Attack!	N/A	Only for use if your website is currently under a DDoS attack

I always like to whitelist the google user agent from this rule, just to be safe. Cloudflare can weed out fake googlebots most of the time. 
Personally I captcha everything above threat score 14. But you should lower this if you are attacked very often.

## ASN:
Use at your own risk. While i recommend blocking providers like arubacloud, digitalocean and contabo, this list is not tested
```
(ip.geoip.asnum in {14061 60631 28438 60592 30823 4134 32505 27715 22773 30823 131090 135905 55330 16629 4755 53363 34549 135330 47285 60798 207590 203087 198651 43289 14576 207319 201978 208425 201094 18978 52000 204601 199883 8220 36351 45011 8560 23969 45629 20207 6471 8075 45899 31400 208556 12271 7552 26496 21769 6876 45102 5617 199490 35816 131293 20860 31898 131428 8881 25429 29802 4788 3326 39284 13448 46484 174 577 29286 5056 9009 63949 212708 40788 12989 11351 11426 7029 42652 18403 54538 209 62044 3269 395003 8100 4190 12874 19740 197540 45458 136258 50837 51852 4826 195 49588 57613 34248 197099 29287 29066 30083 9534 42905 35804 45012 7303 25961 61317 5610 35320 262187 263693 20552 266706 49327 47232 32098 28429 3255 28431 14117 18734 24088 263196 41096 52228 8069 398101 28725 132196 61154 58199 6877 265537 32097 62240 3329 3329 3329 6830 133199 12334 270110 22884 54600 213375 206092 41009 213251 36444})
```

## user agent
Firewall > Tools > User Agent Blocking > Create Blocking Rule
User agent (will show your site as offline in some tools, but it makes life harder for attackers, optional):
```
CyotekWebCopy/1.8 CyotekHTTP/3.0 > Block
CyotekWebCopy/1.8 CyotekHTTP/1.1 > Block
CyotekWebCopy/1.8 CyotekHTTP/2.0 > Block
Wget/1.20.3 (mingw32) > Block
CheckHost (https://check-host.net/) > Block 
node-fetch/1.0 (+https://github.com/bitinn/node-fetch) > Block
Mozilla/4.5 (compatible; HTTrack 3.0x; Windows 98) > Block
```

## SSL
This will block some dumb bots, and make attacks heavier on the attacker.
```
SSL > Full
SSL > SSL/TLS Recommender > ON
SSL > Edge Certificates > Always Use HTTPS > ON
SSL > Edge Certificates > Automatic HTTPS Rewrites > ON
SSL > Edge Certificates > TLS 1.3 > ON
SSL > Edge Certificates > Opportunistic Encryption > ON
SSL > Edge Certificates > Minimum TLS Version > v1.2
```


# Important: block cloudflare access to your backend server.
Attackers can often still find your backend IP through a ssl certificate or host header spoofing. It is recommended to block non-cloudflare traffic.
For how to do that, see https://frankindev.com/2020/11/18/allow-cloudflare-only-in-nginx/

As always, i recommend using nginx and not cloudflare. It is generally more optimized for this kind of high-performance processing.
