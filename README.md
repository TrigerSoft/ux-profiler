# ux-profiler

This project is part of TrigerSoft product line. ux-profiler is a chrome extension.

# Overview

* The first purpose of ux-profiler is to answer a question: "How much time does it take the user to perform an action?". When an action involves network requests, timeouts, requires etc, it's not simple to track these and see the whole picture. ux-profiler does exactly that, tracks and groups related operations and shows it graphicaly, calling it "User Transactions".

* The second purpose of ux-profiler is to profile operations that are processed too much time. Just add an operation to Profiles and re-run the "User Transaction". The profiling session of the specified operation and only it will be created under Profiles Chrome tab.

# User Transaction columns

* **User Time**: Total time elapsed from user perspective for an operation and its "children"
* **Self/Total Time**: Self/Total processing (JavaScript execution) time, without delays and waits.
* **Delay From Parent**: For a child operation, time elapsed since the parent operation ended. Can be negative for the nested events.
*  **Delay From Invocation**: For a child asynchronous operation, time elapsed since the request (timeout/network/...).
*  **Exception**: Boolean indicating whether an exception was thrown during processing.
*  **Timeline**: Graphical relative timeline, useful for comparison of different operations in the _same transaction_. Each line includes:
 * **Delay**
 * **Self Work Time**
 * **Children User Time**
 
 In total, 3 these produce the total user time of the operation and its children.
