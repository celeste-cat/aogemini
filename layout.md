general disclaimer that i'm probably not implementing login system/voting unless i can somehow figure out
a way to safely handle user sessions, cause.. handling the password through to ao3 feels sketchy as fuck
and i don't think i can safely/reliably handle sessions per gemini session
_sidenote:_ maybe i can do sessions by performing a login (with encrypted password against ao3 endpoints) and then give the user a token that expires? just return a string of text and every time you want to perform a logged-in action (kudos, comment even?) input user for the token


# Frontpage

## banner/s (reused)
probably easiest with a code tag? though there are links
maybe using a sort of.. reference? say `[1]` inside the code tag then linking it below it with a simple link `=> https://whatever [1]`

## quick links (find your fav.)
just a quich bunch of links to the respective pages

## news
fetch list of news headers (links), put the publication info as a code line? 
then the rest of the text below it, repeat the `Read more...` link below brief


# Fandoms

## all fandoms
headers per category with respective link to the fandom's listing
add an "All [Fandom]" link per fandom


# browse
keeping in mind that we do not have dropdowns or anything remotely fancy, 
i think the browse page should be a simple listing page that shows something similar to:

```gem
=> /works Browse recently uploaded works
=> /bookmarks Explore works that've been bookmarked recently!
=> /tags Fancy cloud of tags...
=> /collections Where works are collected into collections
```

## general listings
okay so the general problem with work listings is that we have multiple elements to account for:
- hazard quadrant (archive symbols, quick rating)
- general info (title, author, fandom, date published)
- warning/taglist
- brief intro
- metadata (language, wordcount, chapters, hits)

a lot of this info can be abstracted into different elements (subheadings, links), though the hazard quadrant might be .. difficult ? ao3 renders it with 4 images and we'd need to either: 
- translate the symbols into text and get rid of the image completely
- replicate the quadrant by extracting it from the html fetch, re-rendering it ourselves and embedding it as image?

former is easier and cleaner, latter is a bit hit or miss though "prettier"-- even if admittedly, image embedding in gemini is not a feature

## tag cloud
uhhhhhhhhhhhhhhhhhhhhhhhhhhhhh

## collections
technically could re-use the general listing format, just with different parsing and adding the collection's title somewhere. viable but low priority

# search
okay, so this is the make-or-break for the project. having a built-in search feature
means you don't have to externally source the works you want to read, meaning you 
could make better use of the service... problem is? how the fuck can we expose a -form-
or a multi-paramter search in a web protocol where you can barely get user input in?

it could be possible to make a "Work Search" page that had hyperlinks, each of which popped a text input box, then having a "Search" hyperlink at the bottom

problem.. this means somehow getting url parameters ? like.. for each parameter the user passes we could append it to their current url and hitting "search" would launch the query with all existing parameters?

## works
## bookmarks
## tags
## people
 won't implement


# works/fic itself
