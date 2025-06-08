---
title: Week 10, 1
published_at: 2025-05-15
snippet: Mycelium activity
disable_html_sanitization: true
allow_math: true
---

[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [WebSockets](#websockets-api)

## WebSockets API
  My initial idea was to incorporate WebSockets API for my real-time updates of the houses. This means anyone that changes the 'status' of their house, everyone with the browser link opened can see the changes. 
  <br>
  It's a simple logic but requires some help from Thomas. According to them, my system seems fairly enough without needing to incorporate WebSockets API and instead use somwthing called SSE (server-sent events). It works only one-way, from the server to the clients via HTTP connection. It means when server has new updates, it pushes to broadcast the entire update to clients that have the HTTP connection open. Which is ideal for me because my system didn't need a lot of heavy stuff, only changing the image updates.

<br>
<br>