# Cross Site-Scripting

*It may be useful to understand HTTP requests, endpoints, basic HTML and JS*

## XSS, demistified:

XSS is an input-related web application vulnerability; It is based on the premise that **Your script**[1] which executes code is inserted in an user input field such as a search (://example.com/item?search=payload) goes through a set of precautions *(rarely unexisting, though it may occur in one's dreams or in [2005 MySpace](https://en.wikipedia.org/wiki/Samy_(computer_worm)))*, allowing for exploits to execute on the server-side such as unauthorized token exfiltration [1], retrieval of confidential files [1], and before you let your imagination run wild you will most often test with alerts:
[1]-

``` html + javascript

<script>alert()<script>
#the most simple payload
```

On the technical side, XSS payloads are written in html, javascript and/or php, this only after verifying source code and crafting the payload accordingly, spray & pray automation is often wasted time and compute often leading to high-profile traffic and bans in bug bounty programs. 
Include the following in your doctrine:
##### 1- Assuring execution
A working XSS script takes into consideration each layer of defense and adapted to measures, such as adding extra or substracting "<>" html tags, javascript comments "//"
##### 2- Scout for context
Where is your payload being executed? Inline html (<script>vulnerableFunction.js</script>) differs from externally located code (<script src="/scripts/vulnerableFunction.js">) in payload processing; Adapt your script accordingly
##### 3- Get past both HTML and Javascript encoding/ processing

#### Allegory: 
**tunnel allegory** (WIP)

#### -From execution type, XSS further branches into:

### Reflected XSS

### Stored XSS

### DOM-based XSS
