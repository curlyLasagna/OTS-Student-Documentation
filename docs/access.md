# Microsoft Access 🤮

This is the worst piece of software I have ever got in contact with.

![Meme](https://i.redd.it/yjp0len9a6ka1.png)

## Closing MS Access

- Avoid saying 'yes' when it prompts you to save it. It will save the current filter, so the next person who opens that table will have your filtered list and that might confuse them.

## Importing data into MS Access

- Importing from an Excel file may be handy but its error messages are cryptic and the process takes way too long
- I copy the rows in Excel that I want to use and just paste them into Access. It should be that simple and it's also easier to see where you mess up

### A .mdb file is a reference to a database. Not a copy of the database 😓

I've made the mistake of copying the techInfo.mdb file thinking that I had my own database to play with.

As you can imagine, any testing I've done was reflected back on the actual database. In one instance where I was testing out this import method, I accidentally duplicated each items 4 times in each room for one building. Fortunately I was able to filter out these entries by who created it and remove those duplicates in under a minute. (Don't tell James)
