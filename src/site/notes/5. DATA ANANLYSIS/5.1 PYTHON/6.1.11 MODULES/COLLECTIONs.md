---
{"dg-publish":true,"permalink":"/5-data-ananlysis/5-1-python/6-1-11-modules/collectio-ns/","noteIcon":""}
---

#python 
# DEFAULT DICT 
- **`defaultfdict()`** helps us to *ASSIGN* a **DEFAULT VALUE** to a key *(in case the key doesn't exist in dictionary.)*
- Using Normal Dictionary you get **`Keyerror`** *(if key doesn't exist)*; But with **`defaultdict()`**, you will receive the **DEFAULT VALUE** as an *Output*.
- The **DEFAULT VALUE** can be *INTEGER*, *LIST*, *STRING* & also *CUSTOM FUNCTION*.
## NORMAL DICTIONARY
```Python 
normal_dict = {}

print(normal_dict['missing_key'])  
# This will raise a KeyError because 'missing_key' does not exist.
```
## DEFAULT DICTIONARY
```Python 
from collections import defaultdict

# Create a defaultdict with default value as an integer (default 0)
default_dict = defaultdict(int)
print(default_dict['missing_key']) 

# Now, 'missing_key' has been added with the default value 0
print(default_dict)
```

```Output
0
defaultdict(<class 'int'>, {'missing_key': 0})
```

## DEFAULT DICTIONARY
### LIST as DEFAULT 
```Python 
from collections import defaultdict

# Create a defaultdict with default value as a list
default_dict = defaultdict(list)

# Appending value to 'key1'
default_dict['key1'].append('value1')

print(default_dict) 
```

```Output
defaultdict(<class 'list'>, {'key1': ['value1']})
```

### CUSTOM FUNCTION as DEFAULT
```Python 
from collections import defaultdict

# Create a defaultdict with a lambda as default value
default_dict = defaultdict(lambda: 'default_value')

print(default_dict['missing_key'])
```

```Output
default_value
```