# Notes — IP Addresses and Ports

## IP Address Quick Reference

| Type | Format | Example |
|---|---|---|
| IPv4 | 4 numbers, 0–255, dot-separated | 192.168.1.1 |
| IPv6 | 8 groups of 4 hex digits | 2001:db8::1 |
| Localhost | Always 127.0.0.1 | 127.0.0.1 |
| Private | 192.168.x.x / 10.x.x.x | 192.168.0.100 |

## Common Ports Cheat Sheet

| Port | Service |
|---|---|
| 80 | HTTP |
| 443 | HTTPS |
| 22 | SSH |
| 21 | FTP |
| 25 | SMTP (email) |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 27017 | MongoDB |
| 3000 | Node.js dev server |
| 5173 | Vite (React) dev server |
| 8080 | Alternative HTTP |

## Key Commands

```bash
# Find your IP address (Mac/Linux)
ifconfig

# Find your IP address (Windows)
ipconfig

# Find a website's IP
nslookup github.com

# Check if a port is open
telnet localhost 3000

# See what's running on a port (Mac/Linux)
lsof -i :3000
```

## Key Concepts

- **IP Address** — Unique identifier for a device on a network
- **Port** — Identifies a specific service on a device
- **Localhost** — 127.0.0.1 — always your own machine
- **Private IP** — Used inside your home/office network
- **Public IP** — Used on the internet
- **Well-known ports** — 0–1023, reserved for standard services
- **Ephemeral ports** — 49152–65535, used temporarily by clients

## Common Mistakes

- Confusing localhost (127.0.0.1) with your network IP (192.168.x.x)
- Forgetting that HTTP uses port 80 and HTTPS uses port 443 by default
- Trying to run two servers on the same port (causes "port already in use" error)
- Confusing IPv4 and IPv6 formats
