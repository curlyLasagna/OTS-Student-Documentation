## Staging Data
The purpose of the staging data excel sheet is, as the name suggests, is a draft to what components are added or removed from the room.  
The quality and the quantity of the photos you took during the room visit is very important as it gives you a more accurate count of what's in the room 
## Excel Staging Data Template
- 

## Excel formulas 

``` sql
-- Get CATEGORY
-- You might have to re-reference the ITEM_COST file if you get #. 
=VLOOKUP(C2, '[ITEM_COST (version 2).xlsx]ITEM_COST'!$A:$B, 2, FALSE)

-- Get MFG
=IF(SUM(ISNUMBER(SEARCH("Middle", C2))) >= 1, TRIM(LEFT(C2, FIND("^",SUBSTITUTE(C2, " ", "^", 2)&"^"))), LEFT(C2,FIND(" ",C2)-1))

-- Get MODEL
=TRIM(RIGHT(C2, LEN(C2)-LEN(E2)))

-- Return image title
=TRIM((CONCAT("ITEMS_",D2,"_",E2,"_",F2)))
```