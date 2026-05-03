# Notes — Internet Basics Cheat Sheet

## Key Terms

---

### 🌐 Internet
A global network of billions of computers and devices connected together, communicating using shared rules (protocols). Not the same as the World Wide Web — the web is just one service that runs *on top of* the internet.

---

### 📋 Protocol
A set of rules that computers agree to follow when communicating. Like a language — both sides must speak the same one.
- **TCP/IP** — the foundational protocol of the internet
- **HTTP/HTTPS** — for web pages
- **SMTP** — for email
- **FTP** — for file transfers

---

### 📦 Packet
A small chunk of data. Large files are broken into many packets, sent separately, and reassembled at the destination. Each packet contains:
- The data itself
- Source IP address
- Destination IP address
- Sequence number (so packets can be reassembled in order)

---

### 🏠 IP Address
A unique numerical label assigned to every device on a network.
- **IPv4 example:** `192.168.1.1` (32-bit, ~4 billion addresses)
- **IPv6 example:** `2001:0db8:85a3::8a2e:0370:7334` (128-bit, virtually unlimited)

---

### 📶 Bandwidth
The maximum amount of data that can be transmitted over a connection in a given time. Measured in Mbps (megabits per second) or Gbps.
- High bandwidth = more data at once (like a wide highway)
- Low bandwidth = less data at once (like a narrow road)

---

### ⏱️ Latency
The time it takes for a packet to travel from source to destination. Measured in milliseconds (ms).
- Low latency = fast response (good for gaming, video calls)
- High latency = slow response (laggy experience)
- Also called **ping** in gaming contexts

---

### 🏢 ISP (Internet Service Provider)
The company that provides your internet connection. Examples: Comcast, AT&T, Verizon, BT, Vodafone. Your ISP connects your home/office to the broader internet.

---

### 📖 DNS (Domain Name System)
The "phone book" of the internet. Translates human-readable domain names (like `google.com`) into IP addresses (like `142.250.80.46`) that computers can use.

---

### 🔓 HTTP (HyperText Transfer Protocol)
The protocol used to transfer web pages. When you visit a website, your browser sends an HTTP request and the server sends back an HTTP response.

---

### 🔒 HTTPS (HTTP Secure)
HTTP with encryption added (via TLS/SSL). The data is encrypted so no one can intercept and read it. Always use HTTPS for anything sensitive. You can tell by the padlock icon in the browser.

---

## Quick Reference Table

| Term | One-Line Definition |
|------|---------------------|
| Internet | Global network of connected computers |
| Protocol | Agreed-upon rules for communication |
| Packet | Small chunk of data sent over a network |
| IP Address | Unique address for a device on a network |
| Bandwidth | How much data can flow at once |
| Latency | How long data takes to travel |
| ISP | Company providing your internet access |
| DNS | Translates domain names to IP addresses |
| HTTP | Protocol for transferring web pages |
| HTTPS | HTTP with encryption (secure) |

---

## Remember

```
You → Router → ISP → Internet → DNS → Server → Response → You
```

Every time you visit a website, this journey happens in milliseconds.
