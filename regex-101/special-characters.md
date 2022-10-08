# Special Characters

## Caret Sign ^:  Line Start Selection

Use caret sign to match only strings at the beginning of a line.

```
1. 3 eggs, beaten			/^[0-9]/gm			1
2. 1 tsp sunflower oil		/^[0-9]/gm			2
```
```
3. 1 tsp butter				/^./gm			3
3. 1 tsp butter				/^../gm			3.
3. 1 tsp butter				/^.../gm			3.SP
3. 1 tsp butter				/^..../gm			3.SP1
```

## Dollar Sign $: End of Line Selection

Use dollar sign to match only text at the end of a line.

```
https://domain.com/what-is-html.html			/html$/gm		html
https://website.com/html5-features.html		/html$/gm		html
```

```log
https://otherdomain.com/html-elements			/.$/gm		s
https://otherdomain.com/html-elements			/..$/gm		ts
https://otherdomain.com/html-elements			/...$/gm		nts
https://otherdomain.com/html-elements			/....$/gm		ents
```