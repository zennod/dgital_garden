---
{"dg-publish":true,"permalink":"/2-full-stack/java-and-dsa/java-enum/java-enum/","noteIcon":""}
---

#java 
# ENUM 
- **ENUM** is a *class* that represents a *group of **constant*** 
	- *Unchangeable* (**`final`**)
- Used when *Defining Constants* - that are not going to change

> [!important]
> - The difference between **`enum`** & **`class`** is that - 
> 	1. ENUMs constants are **`public`**, **`static`** & **`final`** - *(Can't be Overridden -Unchangeable)*
> 	2. Enum can't be used to *Create `Objects`* 
> 	3. **Can't** **`extend`** classes, but **can** **`implement`** interfaces.

***
- Defining **`ENUM`** - 
```Java
enum Devices{
	LAPTOP,
	PHONE,
	TAB,
	SMARTWATCH
}
```
- Accessing **`ENUM`**
```Java
Devices var_name = Devices.PHONE;
```
***
## EXAMPLE 
```Java
public class Main {
	enum Devices{
		LAPTOP,
		PHONE,
		TAB,
		SMARTWATCH
	}

  public static void main(String[] args) {
    Devices var_name = Devices.PHONE;
    System.out.println(var_name);
  }
}
```
***
***
# ENUM LOOP 
- We can use **`values()`** method, which returns an *`array of all enum`*
```Java 
for (Devices var_name : Devices.values()){
	System.out.println(var_name)
}
```