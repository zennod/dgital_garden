---
{"dg-publish":true,"permalink":"/5-data-ananlysis/5-1-python/6-1-11-modules/json/","noteIcon":""}
---

#python 

- JSON allows us to fetch a **REQUEST** *response* into a *file* or just to *read* by using various **JSON** *functions and methods.*
- The build-in JSON module helps us to *encode PYTHON OBJECTs into JSON string & vice-versa.*
***
# 1. JSON DUMP 
- **`json.dump()`** allows us to **SAVE** the *JSON data* into a **FILE**.
- It basically takes *two* parameters **`json.dump(json_data, file_variable)`**
- Also, takes various other parameters to do certain stuffs *(such as, Sorting, Indentation, Set Separators)*
## STEPs
- First, you need to **OPEN a FILE** with [[5. DATA ANANLYSIS/5.1 PYTHON/6.1.8 FILE HANDLING/2.3.8.1 READING A FILE#MODES\|FILE MODE]] using 
	- **`with open("filename.json, "file_mode") as file_variable_name:`**
- Then, use **`json.dump(json_data_name, file_variable_name)`**
### EXAMPLE 
```Python
import requests
import json

# Make the GET request to the horoscope API
response = requests.get("https://horoscope-app-api.vercel.app/api/v1/get-horoscope/daily?sign=capricorn&day=today")
data = response.json()  # Convert the response to JSON

# Store the JSON data in a file
with open("horoscope_data.json", "w") as file:
    json.dump(data, file)

print("Data stored successfully!")

# Open the JSON file in terminal 
with open("horoscope_data.json") as json_file:
	print(json.load(json_file))
```

```Output
Data stored successfully!
```
***
***
# 2. JSON LOAD
- **`json.load()`** helps us to **READ** a **JSON file**. 
- It takes the **FILE OBJECT** as an *argument* and returns **JSON DATA** in the form of ***Python Objects*** such as *dictionaries, lists, strings, numbers, Booleans, and null values.*
## STEPs
- To read you need to **OPEN a FILE** with [[5. DATA ANANLYSIS/5.1 PYTHON/6.1.8 FILE HANDLING/2.3.8.1 READING A FILE#MODES\|FILE MODE]]  using:
	- **`with open("filename","file_mode") as "file_variable_name)`**
- Then, use **`json.load("file_variable_name)`**
### EXAMPLE 
```Python
with open("horoscope_data.json") as json_file:
	print(json.load(json_file))
```

```JSON 
// Output
{
  "data": {
    "date": "Jun 3, 2023",
    "horoscope_data": "The forecast today is stormy. You may         have sensed that there was some tension clouding.
  },
  "status": 200,
  "success": true
}
```
***
***
# 3. JSON DUMPS
- **`json.dumps()`** helps us to format the saved file **FORMATTING**.
- It take various paramaters.


***
***
# PYTHON DICTIONARY TO JSON 
- We can achieve this by using **`json.dump()`**
```Python 
import json

# Python dictionary
data = {
    "name": "Xerxeus",
    "age": 23,
    "email": "xxxx@example.com"
}

# Convert dictionary to JSON string
json_str = json.dumps(data)

# Print the JSON string
print(json_str)
```

```JSON
// Output
{"name": "Xerxeus", "age": 23, "email": "xxxx@example.com"}
```

***
***
# JSON TO PYTHON DICTIONARY 
- We can achieve this by using **`json.loads()`**
```Python
import json

# JSON string
json_str = '{"name": "Xerxeus", "age": 23, "email": "xxxx@example.com"}'

# Convert JSON string to Python dictionary
data = json.loads(json_str)

# Access the dictionary values
print(data["name"])
print(data["age"])
print(data["email"])
```

```Output
Xerxeus
23
xxxx@example.com
```