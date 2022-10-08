# Character Classes

## Literal Matching

```log
I am curious to know					/curious/gm		curious
“Take limits of your field of vision"		/of/g				of of 		 
```

## Dots

A Dot matches any character.

```
abcABC123 .:!?		/./g			a b c A B C 1 2 3 . : ! ?
abcABC123 .:!?		/../g			ab cA BC 12 3 .: !?
abcABC123 .:!?		/.../g		    abc ABC 123 .: !?
abcABC123 .:!?		/..../g		    abcA BC12 3.:  !?
az 09 _- = :;		/./g			a  z SP 0 9 SP _ - SP = SP : ;	(SP = single whitespace)
```

## Character Sets [abc]

If one of the characters in a word can be various characters, we write it in square brackets [] with all alternative characters. 

```
bar ber bir bor bur		/b[a]r/g		bar
bar ber bir bor bur		/b[e]r/g		ber
bar ber bir bor bur		/b[i]r/g		bir
bar ber bir bor bur		/b[au]r/g		bar bur
bar ber bir bor bur		/b[aeiou]r/g	bar ber bir bor bur
beer deer feer			/[bdf]eer/g	beer deer feer
```

## Negated Character Sets [^abc]

To find all words in the text without the repeacted single character options, use this

```log
bar ber bir bor bur		/b[^a]r/g		ber bir bor bur
bar ber bir bor bur		/b[^i]r/g		bar ber bor bur
bar ber bir bor bur		/b[^aiu]r/g	ber bor 
bear beor beer beur		/be[^ou]r/g	bear beer
```

## Letter Range [a-z]

To find the letters in the specified range, the starting letter and the ending letter are written in square brackets [] with a dash between them "-". It is case-sensitive. 

```log
abcdefghijklmnopqrstuvwxyz		/[a-z]/g	a b c d e f g h i j k l m n o p q r s t u v w x y z
abcdefghijklmnopqrstuvwxyz		/[a-h]/g	a b c d e f g h ijklmnopqrstuvwxyz
abcdefghijklmnopqrstuvwxyz		/[h-t]/g	abcdefg h i j k l m n o p q r s t uvwxyz
abcdefghijklmnopqrstuvwxyz		/[g-k]/g   abcdefg g h i j k mnopqrstuvwxyz
```


## Number Range[0-9]

To find the numbers in the specified range, the starting number and the ending number are written in square brackets [] with a dash - 


```
0123456789		/[0-9]/g		0 1 2 3 4 5 6 7 8 9
0123456789		/[2-5]/g		01 2 3 4 5 6789
0123456789		/[3-6]/g		012 3 4 5 6 789
```


---

## Word Character \w: Alphanumeric with Underscore 

The expression lowercase "\w" is used to find letters, numbers and underscore characters. 
So, \w == [A-Za-z1-3_]

Capital \W does the opposite.

```
abcABC123 _.:!?				/\w/gm		a b c A B C 1 2 3 _
abcABC123 _.:!?				/\W/gm		 SP . : ! ?
```


## Number Character \d and \D (reverse)

Smaller case \d is used to find only number characters.
So, \d == [0-9]

Capital case \D does the opposite.

```
abcABC123 .:!?				/\d/gm		 1 2 3
abcABC123 .:!?				/\D/gm		 a b c A B C SP . : ! ?
```

## Space Character \s

\s is used to find only space characters. Uppercase \S does the opposite.

```
abcABC123 .:!?				/\s/gm		 SP
abcABC123 .:!?				/\S/gm		 a b c A B C . : ~ ?
```