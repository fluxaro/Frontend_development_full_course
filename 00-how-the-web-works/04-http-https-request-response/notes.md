# Notes — HTTP & HTTPS Cheat Sheet

## HTTP Methods

| Method | Safe? | Idempotent? | Has Body? | Use Case |
|--------|-------|-------------|-----------|----------|
| GET | ✅ | ✅ | ❌ | Fetch data |
| POST | ❌ | ❌ | ✅ | Create resource |
| PUT | ❌ | ✅ | ✅ | Replace resource |
| PATCH | ❌ | ❌ | ✅ | Partial update |
| DELETE | ❌ | ✅ | Optional | Remove resource |
| HEAD | ✅ | ✅ | ❌ | Check resource exists |
| OPTIONS | ✅ | ✅ | ❌ | CORS preflight |

- **Safe** = doesn't change server state
- **Idempotent** = calling it multiple times has the same result as calling it once

---

## Status Codes

### 2xx — Success ✅
| Code | Name | When You See It |
|------|------|----------------|
| 200 | OK | Standard success response |
| 201 | Created | POST succeeded, new resource created |
| 204 | No Content | DELETE succeeded, nothing to return |
| 206 | Partial Content | Range request (video streaming) |

### 3xx — Redirection 🔀
| Code | Name | When You See It |
|------|------|----------------|
| 301 | Moved Permanently | URL changed forever (update bookmarks) |
| 302 | Found | Temporary redirect |
| 304 | Not Modified | Browser can use cached version |
| 307 | Temporary Redirect | Like 302 but preserves method |
| 308 | Permanent Redirect | Like 301 but preserves method |

### 4xx — Client Errors ❌
| Code | Name | When You See It |
|------|------|----------------|
| 400 | Bad Request | Malformed request syntax |
| 401 | Unauthorized | Not logged in |
| 403 | Forbidden | Logged in but no permission |
| 404 | Not Found | Resource doesn't exist |
| 405 | Method Not Allowed | Wrong HTTP method used |
| 409 | Conflict | Resource already exists |
| 422 | Unprocessable Entity | Validation failed |
| 429 | Too Many Requests | Rate limited |

### 5xx — Server Errors 🔥
| Code | Name | When You See It |
|------|------|----------------|
| 500 | Internal Server Error | Generic server crash |
| 501 | Not Implemented | Feature not supported |
| 502 | Bad Gateway | Upstream server error |
| 503 | Service Unavailable | Server down/overloaded |
| 504 | Gateway Timeout | Upstream server timed out |

---

## Common Headers

### Request Headers
| Header | Purpose | Example |
|--------|---------|---------|
| `Host` | Target domain | `Host: www.example.com` |
| `User-Agent` | Browser/client info | `User-Agent: Mozilla/5.0...` |
| `Accept` | Accepted content types | `Accept: text/html, application/json` |
| `Accept-Language` | Preferred language | `Accept-Language: en-US,en;q=0.9` |
| `Accept-Encoding` | Accepted compression | `Accept-Encoding: gzip, deflate, br` |
| `Authorization` | Auth credentials | `Authorization: Bearer <token>` |
| `Content-Type` | Body format | `Content-Type: application/json` |
| `Content-Length` | Body size in bytes | `Content-Length: 348` |
| `Cookie` | Session cookies | `Cookie: session=abc123` |
| `Referer` | Previous page URL | `Referer: https://google.com` |

### Response Headers
| Header | Purpose | Example |
|--------|---------|---------|
| `Content-Type` | Response body format | `Content-Type: text/html; charset=utf-8` |
| `Content-Length` | Response body size | `Content-Length: 1234` |
| `Cache-Control` | Caching instructions | `Cache-Control: max-age=3600` |
| `Set-Cookie` | Set a cookie | `Set-Cookie: session=abc; HttpOnly` |
| `Location` | Redirect URL | `Location: https://new-url.com` |
| `Access-Control-Allow-Origin` | CORS policy | `Access-Control-Allow-Origin: *` |
| `X-Frame-Options` | Prevent clickjacking | `X-Frame-Options: DENY` |
| `Strict-Transport-Security` | Force HTTPS | `Strict-Transport-Security: max-age=31536000` |

---

## HTTP vs HTTPS

```
HTTP:   http://example.com  → Port 80  → Plain text (anyone can read)
HTTPS:  https://example.com → Port 443 → Encrypted (TLS/SSL)
```

**Always use HTTPS for:**
- Login forms
- Payment pages
- Any personal data
- APIs with authentication

---

## Quick Request/Response Example

```
REQUEST:
GET /api/users HTTP/1.1
Host: api.example.com
Authorization: Bearer abc123
Accept: application/json

RESPONSE:
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-cache

[{"id": 1, "name": "Alice"}, {"id": 2, "name": "Bob"}]
```
