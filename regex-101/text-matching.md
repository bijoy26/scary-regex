# Text Matching

## Greedy Matching

Regex does a greedy match by default. This means that the matchmaking will be as long as possible. Check out the example below. It refers to any match that ends in r and can be any character preceded by it. But it does not stop at the first letter r


`ber beer beeer beeeer		/.*r/		ber beer beeer beeeer`


## Lazy Matching
Lazy matchmaking stops at the first matching. Add a `?` after `*` to find the first match that is preceded by any character.


`ber beer beeer beeeer		/.*?r/	ber`