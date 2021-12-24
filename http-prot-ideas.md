# L7 http(s) prot ideas

## non-bot verification

- simple redirect: just redirect to yourself with a special url arg, will stop simple bots

- cookie: set a cookie and read again

- captcha (non-interaction) preferably, or interaction if highly suspcious but not block-worthy.

- cooke+aes: set a cookie through js and have the frontend decrypt it and send it back for verification (against scraping)

- localstorage: a lot of cookie pots don't suppor this so it's a great alternative

- dom-based: select specific dom elements, manipulate them, and return the state or final execution. Maybe look for optimizations that browser do to html.


## pre-verification

- detect webhooks and give them bypass, but hard ratelimit & check asn. Http can't be spoofed

- bad countries are bad

- public bad ip lists & scrapers.
