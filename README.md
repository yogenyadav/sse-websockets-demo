Its a demo of websockets versus server side events. While websockets is a 2 way client server communication protocol, using sse only server can send events to client; while different, the sse is well supported by both browsers and mobile devices and most major backends. sse is a far simpler protocol as compared to websockets. also sse being built on http, it can use all the http benefits like http2's multiplexing, compressions, cross site highjacking prevention.
- [SSE vs WebSockets vs Long Polling](https://www.youtube.com/watch?v=n9mRjkQg3VE&ab_channel=FestGroup)
- [Websocket protocol](https://datatracker.ietf.org/doc/html/rfc6455)
- [Compression Extensions for WebSocket](https://datatracker.ietf.org/doc/html/rfc7692)
- [Cross-Site WebSocket Hijacking](https://christian-schneider.net/CrossSiteWebSocketHijacking.html#main)
- [Server-Sent Events: the alternative to WebSockets you should be using](https://germano.dev/sse-websockets/)
- [Server-Sent Events, WebSockets, and HTTP (analysis, pros, cons)](https://www.mnot.net/blog/2022/02/20/websockets)

## Dependencies
- python3 
- pip3
- starlette               0.18.0
- uvicorn                 0.17.5
- websockets              10.1
- Reverse proxy - caddy

## Testing
- Start front end - `cd <project root> && sudo start caddy`
- Start back end
  - Method 1: Add python launcher in vscode and run server.py
  - Method 2: command line - `uvicorn --host 127.0.0.1 --port 6001 server:app && uvicorn --host 127.0.0.1 --port 6002 server:app`

## To stop caddy
`ps -ef | grep caddy`
`sudo kill -9 <pid>`

## To stop uvicorn
`ps -ef | grep uvicorn`
`sudo kill -9 <pid>`
