# HTTP vs HTTPS

## What is HTTP?

**HTTP (Hypertext Transfer Protocol)** is the foundation of data communication on the web. It is used to transfer data like HTML pages, images, videos, and more between a web client (browser) and a server.

### How HTTP works:
- A client sends an HTTP request to a server.
- The server processes the request and sends back an HTTP response, usually containing the requested resource.
- HTTP is **stateless**, meaning each request-response pair is independent.

### Use Case:
HTTP is typically used for accessing web pages or APIs where encryption is not required.

---

## What is HTTPS?

**HTTPS (Hypertext Transfer Protocol Secure)** is an extension of HTTP with added security features. It encrypts the communication between the client and server using **SSL/TLS**.

### How HTTPS works:
- Adds a layer of encryption via SSL/TLS, ensuring that data exchanged is secure from eavesdropping or tampering.
- Verifies the authenticity of the server through an SSL certificate.

### Use Case:
HTTPS is essential for secure communication, such as online banking, e-commerce, and protecting sensitive user data.

---

## Key Differences Between HTTP and HTTPS

| Feature         | HTTP                          | HTTPS                           |
|-----------------|-------------------------------|---------------------------------|
| **Security**    | Unencrypted, prone to attacks | Encrypted, secure communication|
| **Port**        | 80                            | 443                             |
| **Certificate** | No SSL/TLS certificate needed | Requires SSL/TLS certificate    |
| **Performance** | Slightly faster               | Slightly slower due to encryption |

---

## Example Commands and Outputs

### 1. Fetching a Webpage (HTTP vs HTTPS)

- Command:
```bash
curl http://example.com
curl https://example.com
```
- Command Output:
```bash
<html>
<head><title>Example Domain</title></head>
<body>...</body>
</html>
```
- Output for both is same, in https what data is encrypted
