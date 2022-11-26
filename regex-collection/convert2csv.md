# Convert Data to CSV format 

## Input : A List of Groups (`University Score, University Name, Address, Rank`)   

```txt
4.1 PEER ASSESSMENT SCORE
University of Pennsylvania
Philadelphia, PA
#17 in Computer Science (tie)

4.1 PEER ASSESSMENT SCORE
University of Wisconsin--Madison
Madison, WI
#17 in Computer Science (tie)

4.1 PEER ASSESSMENT SCORE
Johns Hopkins University
Baltimore, MD
#20 in Computer Science (tie)

4.0 PEER ASSESSMENT SCORE
Purdue University--West Lafayette
West Lafayette, IN
#20 in Computer Science (tie)
```
## Step 1 : Remove "X.X PEER ASSESSMENT SCORE" Lines

## Regex

`/^[0-9]\.[0-9]/g`	

> ### 🔁 Find an replace with **NULL**.

## Output

```

University of Pennsylvania
Philadelphia, PA
#17 in Computer Science (tie)


University of Wisconsin--Madison
Madison, WI
#17 in Computer Science (tie)


Johns Hopkins University
Baltimore, MD
#20 in Computer Science (tie)


Purdue University--West Lafayette
West Lafayette, IN
#20 in Computer Science (tie)
```
---

## Step 2: Add Comma "`,`" at the end of 1st Line

## Regex

`/(^(.)*University(.)*$)/g`

## Output

```
University of Pennsylvania,
Philadelphia, PA
#17 in Computer Science (tie)


University of Wisconsin--Madison,
Madison, WI
#17 in Computer Science (tie)


Johns Hopkins University,
Baltimore, MD
#20 in Computer Science (tie)


Purdue University--West Lafayette,
West Lafayette, IN
#20 in Computer Science (tie)
```
> ### 🔁 Replace with "`\1,`"

---

## Step 3: Add Comma "`,`" at the end of 2nd Line

## Regex

`/(^(.)*, (.)*$)/g`

## Output

```
University of Pennsylvania,
Philadelphia, PA,
#17 in Computer Science (tie)


University of Wisconsin--Madison,
Madison, WI,
#17 in Computer Science (tie)


Johns Hopkins University,
Baltimore, MD,
#20 in Computer Science (tie)


Purdue University--West Lafayette,
West Lafayette, IN,
#20 in Computer Science (tie)
```

> ### 🔁 Replace with "`\1,`"


---

## Step 4: Merge three lines 

## Regex

`/(^(.)*,$)\n((.)*,$)\n((.)*$)/g`

## Output

```
University of Pennsylvania,Philadelphia, PA,#17 in Computer Science (tie)


University of Wisconsin--Madison,Madison, WI,#17 in Computer Science (tie)


Johns Hopkins University,Baltimore, MD,#20 in Computer Science (tie)


Purdue University--West Lafayette,West Lafayette, IN,#20 in Computer Science (tie)
```

> ### 🔁 Replace with "`\1\3\5`"

---

Finally, save the output data in a text file with `.csv` extension and open with spreadsheet tool.