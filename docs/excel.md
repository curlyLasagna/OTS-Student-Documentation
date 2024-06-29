> I hope you don't have to deal with this, future student employee. This form of data entry is pain, which is why I've automated most of it!
> I can't be of much help in this regard. Consult with other employees

I created an Excel sheet that pulls in data from the `techinfo` SQL database that acts as a middle man between the formulas I've created

The file is named ITEMS_COST. Please feel free to reach out to me on WebEx or through my Github for those files. I'm more than happy to walk you through the process.

## Staging Data

- The purpose of the staging data Excel sheet is, as the name suggests, a draft of what components are added or removed from the room.
- The quality and the quantity of the photos you took during the room visit is very important as it gives you a more accurate count of what's in the room
- The staging data should imitate the MS Access structure so you can easily paste it into the database without issue.

### Lazy approach

Just copy paste what you have in Excel over to Access

### Excel formulas for staging sheet 

These are some of the formulas in my staging sheet 

Make sure to have the ITEMS_COST file in the same working directory as your staging sheet 

``` sql
-- Get CATEGORY
-- You might have to re-reference the ITEM_COST file if it returns a #. 
=VLOOKUP(C2, '[ITEM_COST (version 2).xlsx]ITEM_COST'!$A:$B, 2, FALSE)
```
```sql
-- Get MFG
=IF(SUM(ISNUMBER(SEARCH("Middle", C2))) >= 1, TRIM(LEFT(C2, FIND("^",SUBSTITUTE(C2, " ", "^", 2)&"^"))), LEFT(C2,FIND(" ",C2)-1))
```

```sql
-- Get MODEL
=TRIM(RIGHT(C2, LEN(C2)-LEN(E2)))

-- Return image title
-- Handy for naming image title after you edit the pictures
=TRIM((CONCAT("ITEMS_",D2,"_",E2,"_",F2)))
```
