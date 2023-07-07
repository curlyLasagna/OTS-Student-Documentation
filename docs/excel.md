## Staging Data
- The purpose of the staging data excel sheet is, as the name suggests, is a draft to what components are added or removed from the room.
- The quality and the quantity of the photos you took during the room visit is important as it gives you a more accurate picture of what's in the room
## Excel Staging Data Template
- 

### Lazy approach
Just copy paste 
## Excel formulas 

``` sql
-- Get CATEGORY
-- You might have to re-reference the ITEM_COST file if it returns a #. 
=VLOOKUP(C2, '[ITEM_COST (version 2).xlsx]ITEM_COST'!$A:$B, 2, FALSE)

-- Get MFG
=IF(SUM(ISNUMBER(SEARCH("Middle", C2))) >= 1, TRIM(LEFT(C2, FIND("^",SUBSTITUTE(C2, " ", "^", 2)&"^"))), LEFT(C2,FIND(" ",C2)-1))

-- Get MODEL
=TRIM(RIGHT(C2, LEN(C2)-LEN(E2)))

-- Return image title
-- Handy for naming image title after you edit the pictures
=TRIM((CONCAT("ITEMS_",D2,"_",E2,"_",F2)))
```
