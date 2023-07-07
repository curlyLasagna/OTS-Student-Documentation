# FAQ about the Virtual Tour

## What tech stack do we use for the Virtual Tour website

An executable created using VB to automatically generate a static HTML file for each room. The virtual tour 'script' as other call it, is a misnomer. It's compiled.  
The website is outdated. Refactoring the website is futile.  
It's best to start over.

## What kind of data am I going to be entering?

### Collections

- The number of seats in a classroom with and without a computer in front of it.
- What wireless projector it uses (Mersive or Cisco)

### Items

- The different types of equipment in a room
- The TU tag number of computers

### Item_cost

- A list of each

## What is Access?

- MS Access is a front end that makes your interaction with the database that we use similar to Excel.
  - Essentially, this is the software that you'll have to use to do your usual [CRUD](https://www.codecademy.com/article/what-is-crud)

### Be wary when using Access

- Any changes you make in Access instantly applies to the actual database.
  - You can't 'undo' your way out of it.
- Personally not a fan of using it.
- If you make a mistake, don't feel bad. You're only adding a piece of paper to the landfill.

## What type of database does the Virtual Tour use?

- A windows SQL database
- The Virtual Tour uses this database to grab data from. Any changes you make within the **ITEMS** and **COLLECTIONS** tables will be reflected next time the script is run.

## I can't seem to find my way around the shared network directory

- Me neither.
- Creating a shortcut to a directory that you frequently access is the best thing you can do.
<figure markdown>
![Trash](http://www.hcr-llc.com/hubfs/Images/Blog_Images/Landfill_Problems__Solutions-1.jpg)
<figcaption>Traversing the O: drive</figcaption>
</figure>

## Personal thoughts
Since we interface with the database using Access, it's fairly compatible with Excel.  
However, a lot of the column fields in the database should be automated.  
It gets fairly draining working with spreadsheets when you honestly do not have to.  
This could be achieved by creating an application that you lets enter in only the unique tidbits of information such as what components are added, and quantity. I would argue that that should be the only information that you have to think about, not the date, your name, room number etc.  
That application would communicate with an API that talks directly to the database, so adding data into the database is a lot faster, resulting in less errors and reducing what data a user might erroneously mutate during data insertion.  
With the introduction of Team Dynamix, we could potentially use their Asset feature to store all the information about each component
