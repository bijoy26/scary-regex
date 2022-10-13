# URL Matching 

## Input Type 1: Parse Markdown Table   

```md
| 1      | Hello World            | [Exercise](https://github.com/bregman-arie/devops-exercises/blob/master/topics/shell/hello_world.md)            | [Solution](devops-exercises-shell-scripts/helloworld[Y])     |
| 2      | Basic date             | [Exercise](https://github.com/bregman-arie/devops-exercises/blob/master/topics/shell/basic_date.md)             | [Solution](devops-exercises-shell-scripts/basic-date[Y])     |
```

## Regex

`/(?<=\()https:\/\/.*md(?=\))/g`	

## Output

```
https://github.com/bregman-arie/devops-exercises/blob/master/topics/shell/hello_world.md
https://github.com/bregman-arie/devops-exercises/blob/master/topics/shell/basic_date.md
```
---

## Input Type 2: Parse HTML Source

```html
<html xmlns="http://www.w3.org/1999/xhtml">
   <head>
      <title>Lorem Ipsum</title>
      <meta property="og:title" content="Lorem Ipsum" />
      <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
      <link type="text/css" href="/style.css" rel="stylesheet"/>
      <link rel="shortcut icon" href="#"/>
      <meta property="og:image" content="https://domain.tld" />
   </head>
   <body>
      <div id="main">
      <div id="header">
      <div id="sidebar">
      <div class="section">
      <img src='#' style='margin-left:0.5em' /><br />
      <ul>
         <li><a href="/">loremipsum<big>&#8682;</big></a></li>
      </ul>
      <br />
      <h3><em>Sections</em></h3>
      <ul>
      <li><b>lang</b>: <a href="?blog=1&amp;lang=pl"><img src="#" style="margin: 0" alt="PL" /></a> | <a href="?blog=1&amp;lang=en"><img src="#" style="margin: 0" alt="EN" /></a></li>
      <li><br /></li>
      <li><a href='?id=50'>loremipsum</a></li>
      <li><br /></li>
      <li><a href='https://discord.gg/loremipsum'>&rarr; <span style='background-color:#7087d8;color:white;font-weight:bold;padding-left:0.25em;padding-right:0.25em'>D</span> Discord (chat)</a>
      <li><a href='https://twitter.com/loremipsum'>&rarr; <span style='background-color:#009def;color:white;font-weight:bold;padding-left:0.25em;padding-right:0.25em'>T</span> Twitter</a>
         <br />
```

## Regex

`/(?<=href=("|')).*?(?=("|'))/g`

## Output

```
/style.css
#
/
?blog=1&amp;lang=pl
?blog=1&amp;lang=en
?id=50
https://discord.gg/loremipsum
https://twitter.com/loremipsum
```