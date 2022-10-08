# Flags

Flags `/` modifier change the output of the expression.
Flags determine whether the typed expression treats text as separate lines, is case sensitive, or finds all matches. 

## Global Flag `/g`
The global flag causes the expression to select all matches. If not used it will only select the first match. 


```log
domain.com, test.com, site.com		/\w/			d 	(first match only)
domain.com, test.com, site.com		/\w/g			d o m a i n c o m t e s t c o m s i t e c o m
domain.com, test.com, site.com		/\w+/			domain
domain.com, test.com, site.com		/\w+/g		    domain com test com site com
domain.com, test.com, site.com		/\w+\.com/		domain.com
domain.com, test.com, site.com		/\w+\.com/		domain.com test.com site.com
```

---
## Multiline Flag

Regex sees all text as one line. But we use the **multiline flag** to handle each line separately. In this way, the expressions we write to identify patterns at the end of lines work separately for each line. Now enable the multiline flag to find all matches.


Input paragraph:

```domain.com
test.com
site.com
```


```log
			/\w+\.com/			domain.com site.com 			(read everything as one long line)
			/\w+\.com/g		    domain.com test.com site.com
			/\w+\.com$/m		domain.com					(read line by line)
			/\w+\.com$/gm		domain.com test.com site.com	(multiline with global)
```		
---
## Case-insensitive Flag

In order to remove the case-sensitivity of the expression we have written, we must activate the case-insensitive flag.


## Input paragraph:

```log
DOMAIN.COM
TEST.COM
SITE.COM
```
```
			/\w+\.com$/		NO OUTPUT		 
			/\w+\.com$/i		SITE.COM
			/\w+\.com$/gmi		DOMAIN.COM TEST.COM SITE.COM	 
```

---
