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