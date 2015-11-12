# Easter Eggs

During the contest, we also held an Easter Egg contest for teams who liked poking around at our site. We decided that the eggs would contribute to the actual rankings to motivate people to find them. Here's how it worked:

* 200 bonus points to the team that had the most eggs
* 100 bonus points to the team that had the second-most eggs

Should two teams tie for first, they'd both get 200 points, and same for second place. As it turns out, `RNNF`, an observer team, ended up winning with a score of 12 easter eggs! Then, three teams tied for the second place in the easter egg contest with a score of 8 easter eggs. It happened to be the *same* three teams (`µ's`, `not good at compute box`, and `CatsInBags`) that got perfect scores in the main contest.

Here's the final scoreboard (disregarding time):

    RNNF                    12 egg(s)
    not good at compute box 8 egg(s)
    CatsInBags              8 egg(s)
    µ's                     8 egg(s)
    Avidya                  7 egg(s)
    CCSF_HACKERS            5 egg(s)
    breastmilk              5 egg(s)
    BCCHack                 4 egg(s)

## Writeups

### Easter Egg Page

Similar to Wastebin 2, the Easter Egg rules and submissions page could be found in `robots.txt` of the main site, which contained the following:

    User-agent: *
    Disallow: /95125f09551360c5294d180b013d047d.html
    
Navigating to `95125f09551360c5294d180b013d047d.html` would give you the flag, `egg{gotta_catch_'em_all}`.

### 1337

For this one, you would need to port-scan `web.easyctf.com`.

    failedxyz@backtick:~$ nmap web.easyctf.com -p-
    
    Starting Nmap 6.47 ( http://nmap.org ) at 2015-11-11 22:34 PST
    Nmap scan report for web.easyctf.com (104.131.228.101)
    Host is up (0.085s latency).
    Not shown: 65524 closed ports
    PORT      STATE SERVICE
    22/tcp    open  ssh
    1337/tcp  open  waste
    8001/tcp  open  vcom-tunnel
    10200/tcp open  unknown
    10201/tcp open  unknown
    10202/tcp open  unknown
    10204/tcp open  unknown
    10206/tcp open  unknown
    10207/tcp open  unknown
    10210/tcp open  unknown
    10300/tcp open  unknown
    
    Nmap done: 1 IP address (1 host up) scanned in 24.00 seconds

Navigating to `web.easyctf.com:1337` reveals: `Easter Egg Hunt: egg{9_much_h4kking}`

### 404

The 404 page says:

>Ok, ok, here's your flag. `6567677b6567675f6e6f745f666f756e647d` Just kidding. Click [here](https://www.easyctf.com/) to go back home.

If you `.decode("hex")` the "flag", you'll find that it's actually an easter egg.

```python
>>> "6567677b6567675f6e6f745f666f756e647d".decode("hex")
'egg{egg_not_found}'
```