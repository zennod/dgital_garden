---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-collectio-ns/java-hashmap/","noteIcon":""}
---

#java #Object_Oriented_Programming #java_collection_framework

- Map is like *DICTONARY* - i.e. **KEY**-**VALUE** PAIR.
- Used for *Key - Value Pairs*, *Unique Values*, *Un-Order*

```Java
// General Syntax
HashMap<Obj_type1, Obj_type2> Obj_varName = new Hashmap<>();

// Example
HashMap<Integer, String> map = new HashMap<>();
System.out.println(map)
```

## WHEN TO USE HASHMAP 
1. When associating the **NAMEs** with **VALUES** - *Faster Lookups using KEYs*.
2. Searching data using **UNIQUE** key - *Faster than Looping*
3. Avoiding **`if-else`** or **`switch`** - *Cleaner & Scalable code*
4. Storing data in **KEY** - **VALUE** pair - *Best way to store data*.
5. Counting **frequency** *(i.e. word count, etc)* 
# LOOPING 
- Use **SET** class for the loop of HashMap - 
```Java 
Set<Integer> keys = map.keySet();
for (int i:keys){
	sout(map.get(i))
}
or
for (int i:map.keySet()){
	sout(map.get(i))
}
```

```Java
Set<Map.Entry<Integer,String>> entries = map.entrySet();

for(Map.Entry<Integer,String> entry : entries){
	sout(entry.getKey() + ":" + entry.getValue())
}
```

# METHODs 
1. **PUT** 
- Used for adding the KEY VALUE Pair
```Java
map.put(key, value);
map.put(1,"Xerxeus");
```

2. **GET**
- Used to fetch according to key.
```java
map.get(key);
String s = map.get(3);
```

3. **CONTAINS KEY** 
- Checks if the key exists or not. 
```Java
map.containsKey(key);
map.containsKey(2)
```

4. **CONTAINS VALUE**
- Checks if the value exists or not. 
- Note - Its ***case-sensitive***
```Java
map.containsValue(key);
map.containsValue("Xerxeus")
```

5. **REMOVE**
- Used to remove a key value pair. 
```Java
map.remove(key)
```