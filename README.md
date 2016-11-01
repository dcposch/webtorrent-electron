WebTorrent Electron Process
===

When you're using WebTorrent in an Electron app, like [WebTorrent Desktop](https://webtorrent.io/desktop/), it works best to keep it in a separate process.

The webtorrent.js library needs to run in a *renderer* process, not in the *main* process, because it uses WebRTC. Electron renderer processes are similar to a Chrome tab, while the main process is much like a server-side node.js environment. For more information, check out the [Electron docs]().

This package:
* Creates a hidden window, thereby creating a second renderer process
* Runs `webtorrent.js` in that hidden window
* Provides an API to download or stream torrents, create torrents, receive progress updates, and so on.

Under the hood, it uses Electron's IPC mechanism. Messages are relayed from your UI (renderer process), through the main process, to the WebTorrent hidden window and back.

Quick start
---

TODO
