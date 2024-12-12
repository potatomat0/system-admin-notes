---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: March
day: 17
creation date: 2024-03-17 16:33
modification date: Sunday 17th March 2024 16:33:43
---

#internetContent  #computerScience/networking 
## Article link:
[Site Unreachable](https://www.optimalaltruism.com/a-trans-sentientists-manifesto/)
related notes: 
- [[Linux - SSl, TLS and HTTPS]]
_____
## Content

[![Two computers connected via a proxy server. The first computer says to the proxy server: "ask the second computer what the time is".](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Proxy_concept_en.svg/277px-Proxy_concept_en.svg.png)](https://en.wikipedia.org/wiki/File:Proxy_concept_en.svg)

Communication between two computers connected through a third computer acting as a proxy server. This can protect Alice's privacy, as Bob only knows about the proxy and cannot identify or contact Alice directly.

In computer networking, a proxy server acts as a middleman between your device and the internet. It essentially intercepts your requests for websites or other online resources and relays them on your behalf. Here's a breakdown of how it works:

- **Intermediary:** Instead of connecting directly to a website, your request goes to the proxy server first.
- **Request Handling:** The proxy server can then process the request in different ways, depending on its configuration.
- **Security & Privacy:** It can add an extra layer of security by filtering out malicious content or masking your IP address, making your browsing more private.
- **Performance Boost:** Proxies can also cache frequently accessed data, which can improve loading times for websites you visit often.

There are several different types of proxies used for various purposes:

- **Forward Proxy:** This is the most common type, sitting between you and the general internet.
- **Reverse Proxy:** Used within a private network, it acts as a shield for internal servers, distributing requests and enhancing security.

Here are some other related concepts in networking:

- **Firewall:** Similar to a proxy server, a firewall monitors incoming and outgoing traffic on a network, but it focuses primarily on security by blocking unauthorized access.
- **VPN (Virtual Private Network):** Creates a secure encrypted tunnel between your device and a remote server, offering privacy and anonymity online. While a proxy server masks your IP address, a VPN encrypts your entire internet traffic.
- **Content Delivery Network (CDN):** A network of geographically distributed servers that store website content, aiming to deliver it to users faster based on their location. Proxies can sometimes cache CDN content for further performance improvement.

## Compared to API 

**Proxy Server:**

- **Level:** Operates at the network layer, handling data transfer and communication between devices.
- **Purpose:** Acts as an intermediary between a client (your device) and a server on the internet.
- **Functionality:**
    - Filters content
    - Improves performance by caching data
    - Enhances security by masking IP address
    - Controls access to certain websites

**API (Application Programming Interface):**

- **Level:** Works at the application layer, facilitating communication between software applications.
- **Purpose:** Provides a way for applications to request and receive data from each other in a structured format (like JSON or XML).
- **Functionality:**
    - Defines how applications interact and exchange data
    - Simplifies development by offering pre-built functionalities
    - Allows applications to access data and services from other programs

**Relationship between Proxies and APIs:**

- **Not Direct:** Proxies and APIs don't directly interact with each other.
- **Indirect Connections:**
    - A proxy server can be used to access an API if the API is behind a firewall or restricted to specific locations.
    - Some API gateways (which manage access to APIs) can function like a reverse proxy for internal servers that provide the API functionality.

**Analogy:**

Think of a restaurant. The **proxy server** is like the waiter who takes your order (request) and delivers your food (response) from the kitchen (server). The **API** is like the menu that defines what dishes (data) are available and how to order them (format of requests and responses).

In essence, proxies deal with the overall communication flow between devices, while APIs focus on how software programs exchange specific data in a controlled manner.

Proxy servers are more lower level, they work at the network layer, while API is sitting on top of more abstractions, they work on top of the application layer 