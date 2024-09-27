---
{"dg-publish":true,"permalink":"/5-data-ananlysis/5-1-python/6-1-11-modules/beautifulsoup-4/","noteIcon":""}
---

#python #beautifulsoup #web_scraping
- BeautifulSoup 4 is a *web scraping module* that allows you to *get information* from **HTML** documents and **modify** them as well
# STEPs 
1. First, You need to create a **OBJECT** of Beautifulsoup **CLASS**.
```Python 
#General Syntax
soup = Beautifulsoup(html_page,"html.parser")

#Use case
with open("content.html", "r", encoding="utf-8") as file:
	soup = Beautifulsoup(file, "html.parser")
```

## DIFFERENT USE CASEs 
## FIND TEXT BY TAG 
- Returns only the **FIRST OCCURENCE** of the tag.
```Python 
tag = soup.title
print(tag)
print(tag.string) #Display only the Text within tag.
```

```Output
<title>Hello Xerxeus</title>
Hello Xerxeus
```

### MODIFY STRING VALUE 
- *The modification will take place in the original file too.*
```Python 
tag = soup.title
tag.string = "Hey it's Caesar Here.!!"
print(tag)
```

```Output
<title>Hey it's Caesar Here.!!</title>
```
***
***
## FIND & FIND ALL BY TAG
- **`find(tag_name)`** will return FIRST OCCURENCE of the tag 
```Python 
tag = doc.find("a")
print(tag)
```