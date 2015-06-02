# ux-profiler

This project is part of TrigerSoft product line. ux-profiler is a chrome extension.

### Overview

* The first purpose of ux-profiler is to answer a question: "How much time does it take the user to perform an action?". When an action involves network requests, timeouts, requires etc, it's not simple to track these and see the whole picture. ux-profiler does exactly that, tracks and groups related operations and shows it graphicaly, calling it "User Transactions".

* The second purpose of ux-profiler is to profile operations that are processed too much time. Just add an operation to Profiles and re-run the "User Transaction". The profiling session of the specified operation and only it will be created under Profiles Chrome tab.

### User Transaction columns

* **User Time**: Total time elapsed to perform an operation and its "children" from user perspective.
* **Self/Total Time**: Self/Total processing (JavaScript execution) time, without delays and waits.
* **Delay From Parent**: For a child operation, time elapsed since the parent operation ended. Can be negative for the nested events.
*  **Delay From Invocation**: For a child asynchronous operation, time elapsed since the request (timeout/network/...).
*  **Exception**: Boolean indicating whether an exception was thrown during processing.
*  **Timeline**: Graphical relative timeline, useful for comparison of different operations in the __same user transaction__. Each line includes:
 * _**Delay**_
 * _**Self Work Time**_
 * _**Children User Time**_
 
 In total, 3 these constitute the user time of an operation and its children.

### What kind of events are tracked?

* Any browser events, that are listened using [JQuery](https://jquery.com/) API, e.g. `$(...).click()`. Calling `<element>.addEventListener` directly is not supported.
* XmlHttpRequests (XHR)
* [AMD](https://github.com/amdjs/amdjs-api/blob/master/AMD.md) require/requirejs
* timeouts

### What kind of events are *not* tracked?

* Direct `<element>.addEventListener`.
* setInterval - if used, is not considered is as part of a user transaction.
