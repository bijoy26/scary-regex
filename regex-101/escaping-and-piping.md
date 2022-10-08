# Escaping & Piping 

## Pipe Character |

It allows to specify that an expression can be in different expressions in a group. 
Thus, all possible statements are written separated by the pipe sign |. 

This differs from charset [abc], which operate at the character level. Alternatives are at the expression level. 


```
cat Cat rat		/(C|c)at/g			cat Cat
cat Cat rat		/(C|c)at|rat/g		cat Cat rat
```


## Escape Character \


There are special characters that we use when writing regex. { } [ ] / \ + * . $^ | ? 
Before we can select these characters themselves, we need to use an escape character backslash "\". 

For example, to select the dot . and asterisk * characters in the text, add an escape character \ before it.

```
(*) Asterisk.		/(\*)/g		*
(*) Asterisk.		/(\*|\.)/g		* .
```
---