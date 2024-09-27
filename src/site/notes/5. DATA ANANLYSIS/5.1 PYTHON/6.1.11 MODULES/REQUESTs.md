---
{"dg-publish":true,"permalink":"/5-data-ananlysis/5-1-python/6-1-11-modules/reques-ts/","noteIcon":""}
---

#python #black_hat_python 
- This module is used for  **HTTP REQUESTs AND RESPONSE PURPOSE**.
- You just need to create the object of the request class & use that object.
### Syntax 
**`requests.method_name(param)`**

```Python 
url = https://www.123.com
response = requests.get(url)
json = {'key':'value'}
response = requests.post(url, json)
```
- Here, Response is an object.
- There are multiple request types.
> [!info] Link
> [Python Requests Module](https://www.w3schools.com/python/module_requests.asp)

***
***
# Parameters that can be passed 
**URL** - **`request.methodname(url/'http://www.123.com')`**

**Redirect**- **`request.methodname(allow_redirect = False/True)`** 

**Authentication** - **`request.methodname(url, auth = ('user', 'pass'))`**

**Client Certificate verification** - **`request.methodname(url, cert='folder/myclient.cert')`**

**Cookies **- **`request.methodname(url, cookies = {"favcolor": "Red"})`**

**Header Response** - **`request.methodname(url, headers = {"HTTP_HOST": "MyVeryOwnHost"})`**

**Proxies** -*Send your request via that proxy:* **`request.methodname(url, proxies = { "https" : "https://1.1.0.1:80"})`**

**Steam** - **`request.methodname(url, stream=True)`**
**`request.methodname(url, timeout=0.001)`**

**TLS Certificate Verification** - *Make the request with the path to a TLS certificate:* **`request.methodname(url, verify='folder/tlscertificate')`**