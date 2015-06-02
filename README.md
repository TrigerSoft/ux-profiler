# ux-profiler

This project is part of TrigerSoft product line. ux-profiler is a chrome extension.

# Overview

* The first purpose of ux-profiler is to answer a question: "How much time does it take the user to perform an action?". When an action involves network requests, timeouts, requires etc, it's not simple to track these and see the whole picture. ux-profiler does exactly that, tracks and groups related operations and shows it graphicaly, calling it "User Transactions".

* The second purpose of ux-profiler is to profile operations that take too much time. Just add an operation to Profiles and re-run the "User Transaction". The profiling session of the specified operation and only it will be created under Profiles Chrome tab.

# User Transaction columns

* **User Time**: Total time elapsed from user perspective for an operation and its "children"
* **Self/Total Time**: Self/Total processing (JavaScript execution) time, without delays and waits.
* **Delay From Parent**: For a child operation, time elapsed since the parent operation ended. Since events can be nested, this value can be negative for the nested event.
