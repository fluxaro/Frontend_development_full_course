# 07 — IP Addresses and Ports

## What Is This Lesson About?

Every device on the internet has an address — an **IP address**. And every service running on that device listens on a specific **port number**. Together, IP address + port = the exact location of a service on the internet.

---

## IP Addresses

An IP address is a unique number assigned to every device connected to a network. Think of it like a home address — it tells the internet exactly where to deliver data.

### IPv4

The original format. 32 bits, written as 4 numbers separated by dots:

```
192.168.1.1
142.250.80.46
```

Each number is 0–255. IPv4 supports about 4.3 billion unique addresses — which is no longer enough for all devices on earth.

### IPv6

The newer format. 128 bits, written as 8 groups of 4 hex digits:

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

IPv6 supports 340 undecillion addresses — essentially unlimited.

### Private vs Public IP Addresses

| Type | Range | Used For |
|---|---|---|
| Private | 192.168.x.x, 10.x.x.x, 172.16.x.x | Your home/office network |
| Public | Everything else | The internet |
| Localhost | 127.0.0.1 | Your own computer |

`127.0.0.1` (also called `localhost`) always refers to your own machine. When you run a local development server, you visit `http://localhost:3000` — that is your own computer.

---

## Ports

A port is a number that identifies a specific service or process on a device. If an IP address is like a building address, a port is like an apartment number inside that building.

### Common Ports

| Port | Protocol | Used For |
|---|---|---|
| 80 | HTTP | Unencrypted web traffic |
| 443 | HTTPS | Encrypted web traffic |
| 22 | SSH | Secure shell (remote terminal) |
| 21 | FTP | File transfer |
| 25 | SMTP | Sending email |
| 3306 | MySQL | MySQL database |
| 5432 | PostgreSQL | PostgreSQL database |
| 27017 | MongoDB | MongoDB database |
| 3000 | Custom | Common for Node.js dev servers |
| 5173 | Custom | Vite dev server (React) |
| 8080 | Custom | Common alternative HTTP port |

### How Ports Work in URLs

When you visit `https://github.com`, the browser automatically uses port 443 (HTTPS default). You do not see it in the URL.

When you run a local dev server, you see the port explicitly:
```
http://localhost:3000
http://localhost:5173
```

---

## IP Address + Port Together

The full address of a service is written as `IP:PORT`:

```
192.168.1.1:3000    → Local dev server on your home network
142.250.80.46:443   → Google's HTTPS server
127.0.0.1:5432      → PostgreSQL running on your machine
```

---

## How to Find Your IP Address

**Mac/Linux:**
```bash
ifconfig
# or
ip addr
```

**Windows:**
```bash
ipconfig
```

**Find a website's IP:**
```bash
nslookup github.com
ping github.com
```
