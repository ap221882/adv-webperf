# When we hit the URL

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
