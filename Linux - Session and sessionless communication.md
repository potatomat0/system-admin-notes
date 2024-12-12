---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 09:23
modification date: Thursday 12th December 2024 09:23:35
---

#linux #computerScience/networking #job/vietnix 
## Article link:
[[Linux - stateful and stateless protocol]]
related notes: 
- [[]]
_____
## Content

**Session-Based Communication**

- **Stateful:** The server maintains information about the client's state, such as login credentials, shopping cart items, or preferences.
- **Persistent Connection:** A continuous connection is established between the client and server, allowing for multiple data exchanges within a single session.
- **Examples:** FTP, Telnet, HTTP with cookies.

**Sessionless Communication**

- **Stateless:** The server doesn't maintain any information about the client's state between requests. Each request is treated independently.
- **Stateless Connection:** A new connection is established for each request and terminated after the response is sent.
- **Examples:** HTTP without cookies, DNS, UDP.

**Key Differences**

| Feature     | Session-Based                                          | Sessionless                                   |
| ----------- | ------------------------------------------------------ | --------------------------------------------- |
| State       | Stateful                                               | Stateless                                     |
| Connection  | Persistent                                             | Stateless                                     |
| Security    | Can be more secure (e.g., encrypted sessions)          | **Less secure** (each request is independent) |
| Scalability | Can be less scalable due to state management           | **More scalable** (easier to distribute load) |
| Performance | Can be **slower** due to overhead of maintaining state | Can be faster due to simpler processing       |