# Class Work — IP Addresses and Ports

## What You Will Do

Find your own IP address, look up IP addresses for real websites, and build an HTML reference page documenting what you find.

**Time:** 30 minutes

---

## Activity 1: Find Your Own IP Address (5 minutes)

Open your terminal and run the appropriate command for your operating system:

**Mac/Linux:**
```bash
ifconfig
```
Look for `inet` followed by a number like `192.168.1.x` — that is your local IP address.

**Windows:**
```bash
ipconfig
```
Look for `IPv4 Address` — that is your local IP address.

Write down:
- Your local (private) IP address
- Is it IPv4 or IPv6?
- What range is it in? (192.168.x.x, 10.x.x.x, etc.)

---

## Activity 2: Look Up Website IP Addresses (10 minutes)

Run these commands and write down the results:

```bash
nslookup google.com
nslookup github.com
nslookup youtube.com
```

For each website, write down:
- The IP address returned
- Is it IPv4 or IPv6?

Now try pinging one of them:
```bash
ping google.com
```

Write down:
- What IP address does ping show?
- What is the average response time (latency) in milliseconds?

---

## Activity 3: Explore Ports on Your Machine (5 minutes)

If you have Node.js installed, start a quick server:
```bash
npx serve .
```

Or if you have Python:
```bash
python3 -m http.server 8080
```

Then open your browser and visit `http://localhost:8080` (or whatever port it shows).

Write down:
- What port is the server running on?
- What happens if you visit `http://127.0.0.1:8080` instead of `http://localhost:8080`?

---

## Activity 4: Build an IP and Ports Reference Page (10 minutes)

Create a file called `ip-ports-reference.html`.

Using only HTML, build a reference page that includes:
- An `<h1>` heading
- A `<table>` of common ports (at least 10 rows) with columns: Port Number, Protocol, Used For
- A `<table>` comparing IPv4 vs IPv6
- A `<dl>` defining: IP Address, Port, Localhost, Private IP, Public IP
- Your findings from Activities 1 and 2 in a `<section>` called "My Findings"

---

## Checklist

- [ ] Found your own local IP address
- [ ] Looked up IP addresses for 3 websites
- [ ] Ran ping and noted the latency
- [ ] Built `ip-ports-reference.html` with all required sections
