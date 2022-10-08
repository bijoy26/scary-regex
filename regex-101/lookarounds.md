# Lookarounds

If we want the phrase we're writing to come before or after another phrase, we need to "lookaround".

- **Positive Lookahead (?=)**: Use it to select only the values that have a particular text after them 
- **Negative Lookahead (?!)** : Use it to select only the values that do not have a particular text after them
- **Positive Lookbehind (?<=)** : Use it to select only the values that have a particular text before them
- **Negative Lookbehind (?<!)** : Use it to select only the values that do not have a particular text before them
	
```log
Date: 4 Aug 3PM				/\d/gm		 	 4 3
Date: 4 Aug 3PM				/\dPM/gm		 3PM
Date: 4 Aug 3PM				/\d+(PM)/gm		 3PM
```

```log
Date: 4 Aug 3PM				/\d+(?=PM)/gm		 3
Date: 4 Aug 3PM				/\d+(?=\s)/gm		 4SP
Date: 4 Aug 3PM				/\d+(?!\s)/gm		 3
Date: 4 Aug 3PM				/\d+(?!PM)/gm		 4
```

```log
Product Code: 1064 Price: $5	/\$\d/gm			 $5
Product Code: 1064 Price: $5	/(\$)\d+/gm		     $5
Product Code: 1064 Price: $5	/(?<=\$)\d+/gm		 5
Product Code: 1064 Price: $5	/(?<!\$)\d+/gm		 1064
```