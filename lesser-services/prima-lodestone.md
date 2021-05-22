---
description: Lodestone scraping service.
---

# prima-lodestone

* Language: Go
* Average memory usage: 40MB

[prima-lodestone](https://github.com/PrimaShouji/prima-lodestone) is the service used for interacting with The Lodestone. It is built on [xivapi/godestone](https://github.com/xivapi/godestone). This is used instead of XIVAPI in order to test the underlying library, avoid reliance on XIVAPI's uptime, and to take advantage of the auto-retry features built into the library. While it is completely viable to just make two calls to XIVAPI to handle lookup failures, it is more elegant to simply have that functionality built into the service.

