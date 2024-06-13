# Notes

## When we hit the URL

1- DNS lookup - 100ms
2- TCP connection - 120ms
3- SSL negotiation - 150ms
4- HTTP request - uplink(slower than downlink)
   request - body
5- Server Process(for example 200ms-500ms)
6- HTTP response - downlink
   request - body
7- Browser HTML Parsing
8- Resource discovery (via HTML) and Priority
9- Render engine(layout, paint)

(+80ms each) on cellular networks

But,
LCP Budget is - 2.5 ms

## http

resources- [HTTP Archive](https://httparchive.org)

## Resource discovery queue

Cache headers per file

- Absolute expiration date (1.0)
- Relative expiration date (1.1)
- More specs/values

Browser needs a resource
1> It checks the cache
  A> Cache MISS - we go the network
  B> Cache HIT
    i> it's expired
      conditional request: 1) Not modified (updated cache header) 2) Ok, new file
    ii> it's not expired
      we use the file from the cache

But (i) is like requesting the file initially with new HTTP request so what's the solution?

--- bfcache
