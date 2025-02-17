---
description: Just another simple, fast, and resilient open-source WebSockets server. 📣
---

# 📡 About soketi

![](<.gitbook/assets/carbon (22).png>)

soketi is just another simple, fast, and resilient open-source WebSockets server. 📣

The soketi server is built on top of [uWebSockets.js](https://github.com/uNetworking/uWebSockets.js) - a C application ported to Node.js. uWebSockets.js is demonstrated to perform at levels [_8.5x that of Fastify_](https://alexhultman.medium.com/serving-100k-requests-second-from-a-fanless-raspberry-pi-4-over-ethernet-fdd2c2e05a1e) and at least [_10x that of Socket.IO_](https://medium.com/swlh/100k-secure-websockets-with-raspberry-pi-4-1ba5d2127a23). (_[_source_](https://github.com/uNetworking/uWebSockets.js)_)

soketi implements the [Pusher Protocol v7](https://pusher.com/docs/channels/library\_auth\_reference/pusher-websockets-protocol#version-7-2017-11). Therefore, any Pusher-maintained or compatible client can connect to it, bringing a plug-and-play experience for existing applications that are already compatible with this protocol.

In addition to being a good companion during local development, soketi comes with the resiliency and speed required for demanding production applications.
