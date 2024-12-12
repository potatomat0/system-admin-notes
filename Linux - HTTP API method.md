---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 08:39
modification date: Thursday 12th December 2024 08:39:02
---

#linux #job/vietnix #computerScience/networking 
## Article link:
[HTTP request methods - HTTP | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
[HTTP Methods - REST API Tutorial](https://restfulapi.net/http-methods/)
[[vietnix - API response and their meaning]]
related notes: 
- [[]]
_____

### [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET)

```java
HTTP GET http://www.appdomain.com/users
HTTkP GET http://www.appdomain.com/users?size=20&page=5
HTTP GET http://www.appdomain.com/users/123
HTTP GET http://www.appdomain.com/users/123/address
```

The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data and should not contain a request [content](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_Content).

response would usually be: 200 (ok), 404 (not found), 400 (bad request)

### [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD)

The `HEAD` method asks for a response identical to a `GET` request, but without a response body.

### [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)

The `POST` method submits an entity to the specified resource, **often causing a change in state or side effects** on the server.

```java
POST /test/demo_form.php HTTP/1.1  
Host: w3schools.com  
  
name1=value1&name2=value2
```
**Some notes on POST requests:**

- POST requests are never cached
- POST requests do not remain in the browser history
- POST requests cannot be bookmarked
- POST requests have no restrictions on data length

POST is **neither safe nor idempotent**, and invoking two identical POST requests will result in two different resources containing the same information (except resource ids).

### [`PUT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT)

The `PUT` method replaces all current representations of the target resource with the request [content](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_Content).

### [`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE)

The `DELETE` method deletes the specified resource.

```java
HTTP DELETE http://www.appdomain.com/users/123 
HTTP DELETE http://www.appdomain.com/users/123/accounts/456
```

### [`CONNECT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT)

The `CONNECT` method establishes a tunnel to the server identified by the target resource.

### [`OPTIONS`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS)

The `OPTIONS` method describes the communication options for the target resource.

### [`TRACE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE)

The `TRACE` method performs a message loop-back test along the path to the target resource.

### [`PATCH`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH)

The `PATCH` method applies partial modifications to a resource.

## get vs post 

