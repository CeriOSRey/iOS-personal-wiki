---
title: DispatchQueue
link: https://developer.apple.com/documentation/dispatch/dispatchqueue
---

DispatchQueue: An object that manages the execution of tasks serially or concurrently on your app's main thread or on a background thread.

==Avoid Excessive Thread Creation==
==Attempting to synchronously execute a work item on the main queue results in deadlock.==

Sample inits:

```
DispatchQueue.main.async {}
DispatchQueue.main.sync {}
```
