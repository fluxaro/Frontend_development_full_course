# 03 — DNS Explained

## What Is DNS?

DNS stands for **Domain Name System**. It's often called the "phone book of the internet."

Here's the problem it solves: computers communicate using IP addresses (like `140.82.121.4`), but humans are terrible at remembering numbers. We're much better at remembering names like `github.com`. DNS bridges that gap — it translates human-friendly domain names into machine-friendly IP addresses.

---

## The Phone Book Analogy

Imagine you want to call your friend "Alex." You don't memorize their phone number — you just look up "Alex" in your contacts, and your phone finds the number for you.

DNS works the same way:
- **"Alex"** = `github.com` (the name you remember)
- **Phone number** = `140.82.121.4` (the IP address computers use)
- **Contacts app** = DNS server (does the lookup for you)

---

## How DNS Resolution Works (Step by Step)

When you type `github.com`:

1. **Browser cache** — Has it looked this up recently? Use the cached result.
2. **OS cache** — Check the operating system's DNS cache.
3. **Router cache** — Check your home router's cache.
4. **Recursive Resolver** — Your ISP's DNS server. It does the heavy lifting.
5. **Root Name Server** — Knows where to find `.com` servers.
6. **TLD Name Server** — The `.com` server knows where `github.com`'s records are.
7. **Authoritative Name Server** — GitHub's own DNS server. Returns the IP address.
8. **Result cached** — The IP is cached at each level for future lookups.

```
You → Recursive Resolver → Root NS → TLD NS (.com) → Authoritative NS → IP!
```

---

## Types of DNS Records

| Record Type | Purpose | Example |
|-------------|---------|---------|
| **A** | Maps domain to IPv4 address | `github.com → 140.82.121.4` |
| **AAAA** | Maps domain to IPv6 address | `github.com → 2606:50c0:8000::153` |
| **CNAME** | Alias — points to another domain | `www.github.com → github.com` |
| **MX** | Mail server for the domain | `github.com → aspmx.l.google.com` |
| **TXT** | Text records (verification, SPF) | `"v=spf1 include:..."` |
| **NS** | Name servers for the domain | `github.com → ns1.p16.dynect.net` |

---

## DNS Caching

DNS results are cached (stored temporarily) to speed things up:
- **TTL (Time to Live)** — how long a DNS record is cached (in seconds)
- A TTL of `3600` means the record is cached for 1 hour
- After TTL expires, the lookup happens again

---

## Try It Yourself

Open your terminal and run:
```bash
nslookup google.com
nslookup github.com
nslookup twitter.com
```

You'll see the IP addresses returned for each domain.

---

## Prerequisites

- Lesson 01: Internet Basics
- Lesson 02: What Happens When You Type a URL

## Next Lesson

→ `04-http-https-request-response`
