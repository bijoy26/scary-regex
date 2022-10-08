# Quantifiers 

## Repetitions

Some special characters are used to specify how many times a character will be repeated in the text. 
These special characters are:

- the plus +
	- a plus sign after a character indicates that it can occur at least one or more times
- the asterisk *
	- Asterisk after a character means that it may either not match at all or can match many times.
- the question mark ?
    - A question mark after a character indicates that a character is optional
```	
br ber beer	/be*r/g		br ber beer
br ber beer	/be+r/g		ber
dp dep deep	/de*p/g		dp dep deep
color, colour	/colou?r/g		color colour
a, an			/an?/g		a an
```


## Curly Braces

- To express a certain number of occurrences of a character, at the end we write curly braces {n} along with how many times we want it to occur.
- To express the occurrence of a character in a certain number range, we write curly braces {x,y} with the interval we want to go to the end.
- To express at least a certain number of occurrences of a character, we write the end of the character at least how many times we want it to occur, with a comma , at the end, and inside curly braces {n, }.
	
```
ber beer beeer beeeer		/be{2}r/g		beer
ber beer beeer beeeer		/be{3}r/g		beeer
ber beer beeer beeeer		/be{2,}r/g		beer beeer beeeer
ber beer beeer beeeer		/be{1,4}r/g	ber beer beeer beeeer
ber beer beeer beeeer		/be{2,3}r/g	beer beeer
ber beer beeer beeeer		/be{3,}r/g		beeer beeeer
```

```log
Release 10/9/2021		/[0-9]{4}/g	2021
Release 10/9/2021		/[0-9]{2,}/g	10 2021
Release 10/9/2021		/[0-9]{1,4}/g	10 9 2021
```