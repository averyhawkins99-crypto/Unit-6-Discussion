# Unit-6-Discussion
# Python Dictionaries as Hash Tables

A Python demonstration simulating hash table behavior using built-in dictionaries (`dict`). Using a student gradebook as a practical example, this script walks through core CRUD operations, edge-case handling, and the underlying mechanics of hash functions and constant-time lookups.

## Overview

Under the hood, Python dictionaries are implemented as hash tables. Instead of storing elements sequentially like a list, Python passes each key through a built-in `hash()` function to map it directly to an index (bucket) in an underlying array. This allows data retrieval, insertion, and deletion to execute in **O(1) average time complexity**.

## Features Demonstrated

1. **Insert Operations:** Initializes an empty dictionary and populates it with five student-grade key-value pairs.
2. **Lookup Operations:** Retrieves values using both standard bracket notation (`dict[key]`) and the `.get()` method.
3. **Update Operations:** Overwrites an existing key's value, demonstrating key uniqueness within a hash table.
4. **Delete Operations:** Removes a key-value pair using `.pop()` and explains how Python handles deleted memory slots internally.
5. **Edge Cases:**
   - Safely querying a non-existent key with `.get()` to avoid a `KeyError`.
   - Safely deleting a non-existent key with `.pop(key, default)`.
   - Demonstrating "upsert" behavior when assigning a value to a missing key.

## Prerequisites

- **Python 3.x** (No external libraries or dependencies required)

## How to Run

1. Save the script as `hash_table_demo.py` (or your preferred filename).
2. Open a terminal or command prompt and navigate to the file's directory.
3. Run the script:
   ```bash
   python hash_table_demo.py
   ```

## Sample Output

```text
=== UNIT 6: DICTIONARIES AS HASH TABLES ===

=== INSERT OPERATIONS ===
Inserted 5 student records into the hash table.
Current Hash Table: {'Alice': 92, 'Bob': 85, 'Charlie': 78, 'Diana': 95, 'Evan': 88}

=== LOOKUP OPERATIONS ===
Lookup 'Alice': 92
Lookup 'Diana': 95

=== UPDATE OPERATIONS ===
Before Update: {'Alice': 92, 'Bob': 85, 'Charlie': 78, 'Diana': 95, 'Evan': 88}
Updated 'Bob' from 85 to 90.
After Update: {'Alice': 92, 'Bob': 90, 'Charlie': 78, 'Diana': 95, 'Evan': 88}

=== DELETE OPERATIONS ===
Before Deletion: {'Alice': 92, 'Bob': 90, 'Charlie': 78, 'Diana': 95, 'Evan': 88}
Removed 'Charlie' (Grade: 78) from the hash table.
After Deletion: {'Alice': 92, 'Bob': 90, 'Diana': 95, 'Evan': 88}

=== EDGE CASES ===
Edge Case 1 - Lookup missing key 'Zoe':
Result using .get(): Student not found

Edge Case 2 - Delete missing key 'Zoe' safely:
Result using .pop() with default: Key does not exist, nothing deleted

Edge Case 3 - Updating a missing key 'Frank':
After assigning 'Frank' = 91: {'Alice': 92, 'Bob': 90, 'Diana': 95, 'Evan': 88, 'Frank': 91}
```

## Time Complexity Summary

| Operation | Average Case | Worst Case (Heavy Collisions) |
| :--- | :---: | :---: |
| **Insert** | O(1) | O(n) |
| **Lookup** | O(1) | O(n) |
| **Update** | O(1) | O(n) |
| **Delete** | O(1) | O(n) |
