---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: March
day: 13
creation date: 2024-03-13 11:00
modification date: Wednesday 13th March 2024 11:00:19
---

#internetContent  #computerScience/networking 
## Article link:

related notes:
- [[Linux - What is DNS]]
_____
## Content

The internet thrives on information exchange, but ensuring that information reaches the intended recipient securely is crucial. This lecture explores three key technologies that work together to safeguard online communication: SSL, TLS, and HTTPS.

### 1. Secure Sockets Layer (SSL): The Predecessor

SSL stands for Secure Sockets Layer. Developed by Netscape in the 1990s, it was the first widely adopted protocol for encrypting communication over a network. SSL established a secure connection between a web server and a browser by:

- **Encryption:** SSL scrambled data using encryption algorithms, making it unreadable to anyone intercepting it.
- **Authentication:** SSL employed digital certificates issued by trusted authorities to verify the identity of the server, ensuring you were connecting to the legitimate website.

However, SSL had some security vulnerabilities that were discovered over time. This led to the development of its successor, Transport Layer Security (TLS).

### 2. Transport Layer Security (TLS): The Current Standard

TLS (Transport Layer Security) is the current standard for encrypting internet communication. It emerged from SSL, addressing its security weaknesses and offering several improvements:

- **Stronger encryption algorithms:** TLS utilizes more robust encryption algorithms compared to SSL, making it significantly harder to crack the encrypted data.
- **Improved authentication:** TLS offers more sophisticated methods for server authentication, enhancing security.
- **Ongoing development:** TLS is actively maintained and updated to address emerging security threats.

While SSL is no longer considered secure for most purposes, the terms "SSL" and "TLS" are sometimes used interchangeably.

### 3. HTTPS: Putting TLS to Work

HTTPS (Hypertext Transfer Protocol Secure) is not a separate protocol itself, but rather HTTP (the standard communication protocol for the web) running on top of TLS. Think of HTTPS as the secure version of HTTP.

Here's how HTTPS works:

1. **Browser initiates connection:** When you visit a website secured with HTTPS, your browser attempts to establish a connection with the web server.
2. **TLS handshake:** The browser and server engage in a "handshake" using TLS. This handshake verifies the server's identity and negotiates the encryption algorithms to be used.
3. **Encrypted communication:** Once the handshake is complete, all data exchanged between your browser and the server is encrypted using TLS, ensuring confidentiality and data integrity.

**Benefits of HTTPS:**

- **Confidentiality:** HTTPS protects sensitive information like login credentials, credit card details, and private messages from being intercepted by attackers.
- **Data integrity:** HTTPS ensures that data remains unaltered during transmission, preventing tampering or man-in-the-middle attacks.
- **Trust and authenticity:** The presence of HTTPS in the address bar (indicated by a padlock symbol) signifies a secure connection and a legitimate website, fostering user trust.

**Real-world applications of HTTPS:**

- Online banking and financial transactions
- E-commerce purchases
- Sending and receiving sensitive information (e.g., medical records)
- Logging in to secure accounts

In today's internet landscape, using HTTPS is essential for protecting your online privacy and ensuring secure communication.