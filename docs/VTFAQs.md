# FAQ about the Virtual Tour
Frequently asked questions, at least personally

## What tech stack do we use for the Virtual Tour website
An executable created using VB to automatically generate static HTML files for each room. The virtual tour 'script' as other call it, is a misnomer. It's a compiled program.  
It looks ugly. Refactoring the program is futile.

## What kind of data am I going to be entering?
### Collections
- The number of seats in a classroom with and without a computer in front of it.
- What wireless projector it uses (Mersive or Cisco)

### Items
- The different types of equipment in a room
- The TU tag number of computers

## What type of database does the VT use? 
- A windows SQL database
- The Virtual Tour relies on this database to grab data from. Any changes you make within the **ITEMS** and **COLLECTIONS** will be reflected next time the script is ran.

## What is Access?
- MS Access is a front end that makes your interaction with the database that we use similar to Excel.
  - Essentially, this is the software that you'll have to use to do your usual [CRUD](https://www.codecademy.com/article/what-is-crud)

### What's the worst thing you can do?
- Any changes you make in Access instantly applies to the actual database.
  - You can't 'undo' your way out of it. Be careful when interfacing with Access.
