A map (also known as a dictionary or associative array) is a data structure that stores key-value pairs. Each key is unique, and it allows for efficient retrieval, insertion, and deletion of values based on their keys.

### Types of Maps

1. **Unordered Map (Hash Map)**
2. **Ordered Map (Tree Map)**
3. **Multimap**

Let's discuss each type in detail:

### 1. Unordered Map (Hash Map)

#### Structure
- Implemented using a hash table.
- Keys are hashed to index the underlying array.
- Key-value pairs are not stored in any particular order.

#### Operations and Time Complexity

- **Insert**: O(1) on average
- **Delete**: O(1) on average
- **Search (Lookup)**: O(1) on average
- **Iteration**: O(n)

#### Use Cases
- **Real-World Example**: Storing user profiles where user IDs are the keys.
- **Real-World Example**: Implementing caches for quick data retrieval.

#### Implementation in Python

```python
my_map = {}
my_map['a'] = 1
my_map['b'] = 2
my_map['c'] = 3
print(my_map['a'])  # Output: 1
del my_map['a']
print(my_map)  # Output: {'b': 2, 'c': 3}
```

### 2. Ordered Map (Tree Map)

#### Structure
- Implemented using a balanced binary search tree (e.g., Red-Black Tree or AVL Tree).
- Key-value pairs are stored in sorted order based on the keys.

#### Operations and Time Complexity

- **Insert**: O(log n)
- **Delete**: O(log n)
- **Search (Lookup)**: O(log n)
- **Iteration**: O(n) (in sorted order)

#### Use Cases
- **Real-World Example**: Storing a sorted list of items, such as a list of users sorted by username.
- **Real-World Example**: Implementing ordered collections like time-series data.

#### Implementation in Python

Python’s standard library does not include an ordered map, but you can use the `sortedcontainers` module for this purpose.

```python
from sortedcontainers import SortedDict

my_ordered_map = SortedDict()
my_ordered_map['c'] = 3
my_ordered_map['a'] = 1
my_ordered_map['b'] = 2
print(my_ordered_map)  # Output: SortedDict({'a': 1, 'b': 2, 'c': 3})
```

### 3. Multimap

#### Structure
- Allows multiple values for the same key.
- Can be implemented using a hash table or a balanced binary search tree.

#### Operations and Time Complexity

- **Insert**: O(1) on average (hash multimap), O(log n) (tree multimap)
- **Delete**: O(1) on average (hash multimap), O(log n) (tree multimap)
- **Search (Lookup)**: O(1) on average (hash multimap), O(log n) (tree multimap)
- **Iteration**: O(n)

#### Use Cases
- **Real-World Example**: Storing students' grades where each student (key) can have multiple grades (values).
- **Real-World Example**: Implementing dictionaries where a single key can have multiple associated values, such as a word with multiple definitions.

#### Implementation in Python

Python’s standard library does not include a multimap, but you can use the `collections.defaultdict` to achieve similar functionality.

```python
from collections import defaultdict

my_multimap = defaultdict(list)
my_multimap['a'].append(1)
my_multimap['a'].append(2)
my_multimap['b'].append(3)
print(my_multimap)  # Output: defaultdict(<class 'list'>, {'a': [1, 2], 'b': [3]})
```

### Summary Table

| Operation             | Unordered Map (Hash Map) | Ordered Map (Tree Map) | Multimap (Hash Multimap) | Multimap (Tree Multimap)  |
|-----------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| Insert                | O(1)                     | O(log n)                | O(1)                     | O(log n)                 |
| Delete                | O(1)                     | O(log n)                | O(1)                     | O(log n)                 |
| Search (Lookup)       | O(1)                     | O(log n)                | O(1)                     | O(log n)                 |
| Iteration             | O(n)                     | O(n) (sorted)           | O(n)                     | O(n) (sorted)            |

### When to Use Each Type

- **Unordered Map (Hash Map)**: Use when you need fast lookups, insertions, and deletions without caring about the order of keys. Example: implementing caches or storing user profiles.
- **Ordered Map (Tree Map)**: Use when you need to maintain a sorted collection of key-value pairs with efficient membership tests, insertions, and deletions. Example: keeping a sorted list of items or time-series data.
- **Multimap (Hash Multimap)**: Use when you need to associate multiple values with a single key without caring about the order. Example: storing students' grades or a dictionary with multiple definitions for each word.
- **Multimap (Tree Multimap)**: Use when you need a sorted collection of key-value pairs where each key can have multiple associated values. Example: managing a sorted inventory with quantities.

Each type of map and multimap has its specific advantages and is suited to different scenarios based on the application requirements.
