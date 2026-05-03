# Assignment — IP Addresses and Ports Reference Guide

## What You Are Building

Create an HTML page called `ports-guide.html` that serves as a complete reference guide for IP addresses and ports.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### 1. Introduction
An `<h1>` and introductory paragraph explaining what IP addresses and ports are and why they matter for web developers.

### 2. IPv4 vs IPv6 Comparison Table
A `<table>` with columns: Feature | IPv4 | IPv6

Include rows for: Format, Example, Address length, Total addresses, Current usage.

### 3. Special IP Addresses Section
An `<h2>` and a `<table>` explaining special IP addresses:
- 127.0.0.1 (localhost)
- 0.0.0.0 (all interfaces)
- 192.168.x.x (private network)
- 10.x.x.x (private network)

### 4. Common Ports Reference Table
A `<table>` with at least 15 ports. Columns: Port Number | Protocol | Service | Used By Developers?

### 5. Developer Ports Section
An `<h2>` specifically about ports developers use daily:
- 3000 (Node.js/React)
- 5173 (Vite)
- 8080 (alternative HTTP)
- 5432 (PostgreSQL)
- 3306 (MySQL)
- 27017 (MongoDB)

For each, explain when a developer would encounter it.

### 6. Terminal Commands Section
A `<pre>` block showing the commands to find your IP address on Mac, Windows, and Linux.

---

## What Good Looks Like

- All tables have `<thead>` and `<tbody>`
- All tables have a `<caption>`
- The content is accurate and useful
- The page is well-structured with proper heading hierarchy

---

## Submission

Save as `ports-guide.html` and submit via GitHub.
