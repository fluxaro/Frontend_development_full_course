# Notes — DNS Explained Cheat Sheet

## DNS Record Types

| Type | Name | Purpose | Example |
|------|------|---------|---------|
| **A** | Address | Maps domain → IPv4 address | `github.com → 140.82.121.4` |
| **AAAA** | IPv6 Address | Maps domain → IPv6 address | `github.com → 2606:50c0:8000::153` |
| **CNAME** | Canonical Name | Alias pointing to another domain | `www.github.com → github.com` |
| **MX** | Mail Exchange | Email server for the domain | `github.com → aspmx.l.google.com` |
| **TXT** | Text | Arbitrary text (SPF, verification) | `"v=spf1 include:_spf.google.com ~all"` |
| **NS** | Name Server | Authoritative DNS servers for domain | `github.com → ns1.p16.dynect.net` |
| **PTR** | Pointer | Reverse DNS (IP → domain) | `140.82.121.4 → github.com` |
| **SOA** | Start of Authority | Admin info about the DNS zone | Serial, refresh, retry times |

---

## DNS Resolution Order

When you look up a domain, the resolver checks in this order:

```
1. Browser cache        (fastest — already looked up recently)
2. OS cache             (your computer's DNS cache)
3. Router cache         (your home/office router)
4. ISP Recursive Resolver  (your ISP's DNS server)
5. Root Name Servers    (13 root servers worldwide, know where TLDs are)
6. TLD Name Servers     (.com, .org, .net servers)
7. Authoritative NS     (the domain's own DNS server — final answer)
```

---

## Common DNS Terms

### TTL (Time to Live)
How long a DNS record is cached, in seconds.
- `TTL: 300` = cached for 5 minutes
- `TTL: 3600` = cached for 1 hour
- `TTL: 86400` = cached for 24 hours

Lower TTL = changes propagate faster, but more DNS queries.  
Higher TTL = fewer queries, but changes take longer to propagate.

### DNS Propagation
When you change a DNS record, it takes time for the change to spread across all DNS servers worldwide. This can take minutes to 48 hours depending on TTL.

### Recursive Resolver
A DNS server (usually your ISP's) that does the full lookup on your behalf, querying root servers, TLD servers, and authoritative servers.

### Authoritative Name Server
The DNS server that holds the actual records for a domain. It gives the final, definitive answer.

### Root Name Servers
13 sets of servers (labeled A through M) that know where all TLD servers are. They're the starting point for any DNS lookup.

---

## How DNS Caching Works

```
First visit to github.com:
  Browser → ISP DNS → Root NS → .com NS → GitHub NS → 140.82.121.4
  Result cached for TTL duration

Second visit (within TTL):
  Browser → Browser cache → 140.82.121.4 (instant!)
```

---

## Useful Terminal Commands

```bash
# Basic lookup
nslookup google.com

# Lookup specific record type
nslookup -type=MX google.com
nslookup -type=NS google.com
nslookup -type=TXT google.com

# Using dig (Mac/Linux)
dig google.com
dig google.com MX
dig google.com NS +short

# Trace the full DNS resolution path
dig google.com +trace

# Flush DNS cache
# Windows:
ipconfig /flushdns
# Mac:
sudo dscacheutil -flushcache
# Linux:
sudo systemd-resolve --flush-caches
```

---

## Quick Reference

```
Domain:  github.com
         │
         ├── A record    → 140.82.121.4  (IPv4)
         ├── AAAA record → 2606:50c0:... (IPv6)
         ├── CNAME       → www → github.com
         ├── MX          → mail server
         ├── NS          → ns1.p16.dynect.net
         └── TXT         → SPF, verification strings
```
