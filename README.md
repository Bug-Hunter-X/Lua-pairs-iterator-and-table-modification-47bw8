# Lua pairs iterator and table modification
This example demonstrates a potential issue with Lua's `pairs` iterator when modifying the table being iterated over.  The `foo` function recursively iterates through a nested table. If the table is modified during iteration, it might lead to unexpected results such as skipped entries or even infinite loops.

## Bug
The `bug.lua` file contains code that attempts to recursively traverse a nested table using the `pairs` iterator.  However, it doesn't handle potential issues when modifying the table during traversal.

## Solution
The `bugSolution.lua` file presents a safer approach. It avoids modification during iteration.  Instead, it employs a copy or iterates over a copy to perform the necessary operations without affecting the iteration process.