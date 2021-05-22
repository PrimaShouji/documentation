---
description: Queue password generator.
---

# DailyPasswordGeneratorService

* Language: VB.NET
* Average memory usage: 30MB

DailyPasswordGeneratorService is in charge of providing the passwords used by the queue system. The passwords provided by the service are per-user and change at midnight \(server time\). The repository is private in order to keep the password generation algorithm a secret. I would like to rewrite this in a different programming language eventually, in order to keep its memory usage to a level proportionate to what the service is actually designed to do.



