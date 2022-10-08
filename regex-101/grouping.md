# Grouping & Referencing

## Parentheses (): Grouping

We can group an expression and use these groups to reference or enforce some rules using parenthesis.

```
ha-ha,haa-haa		/(haa)/g		haa haa
ha-ha,haa-haa		/(ha)/g		ha ha ha ha
ha-ha,haa-haa		/(ha)-/g		ha-
ha-ha,haa-haa		/-(ha)/g		-ha -ha
ha-ha,haa-haa		/(ha)-/g		ha-
ha-ha,haa-haa		/(ha)-(ha)/g	ha-ha
ha-ha,haa-haa		/(haa)-(haa)/g	haa-haa
```


## Group Referencing 

In case of multiple groups, same group can be referenced by writing "\n" to avoid repitions. (n= order)
	- \1 denotes the replacement for the first group 
	- \2 refers the second group

```
ha-ha,haa-haa		/(ha)-\1/g			ha-ha		( \1 == (ha) )
ha-ha,haa-haa		/(haa)-\1/g		haa-haa 	( \1 == (haa) )
ha-ha,haa-haa		/(ha)-\1,/g		ha-ha,
ha-ha,haa-haa		/(ha)-\1,(haa)-\2/g	ha-ha,haa-haa
```



## Non-capturing Grouping (?: )

You can group an expression and ensure that it is not captured by references. Mark a non-capturing group with by preceeding it with ?:

`ha-ha,haa-haa		/(?:ha)-ha,(haa)-\1/g		ha-ha,haa-haa`