# Python Interview Questions

## 1. Difference between List and Tuple in Python?
| Feature     | List                       | Tuple             |
| ----------- | -------------------------- | ----------------- |
| Mutability  | Mutable                    | Immutable         |
| Syntax      | `[]`                       | `()`              |
| Performance | Slower (due to mutability) | Faster            |
| Use Case    | Dynamic data               | Fixed/static data |  


## 2. How do sets help in removing duplicates from a list?
- Sets are unordered collections of unique elements.
- When a list is converted to a set, all duplicate values are automatically removed.
- This makes it easy to filter out repeated elements using set(). 
```python
a = [1, 2, 2, 3]
unique = list(set(a))
print(unique)  # Output: [1, 2, 3]
```

## 3. Why are dictionaries faster than lists for lookups?
- Dictionaries are implemented using hash tables, enabling average O(1) lookup time.
- Lists require O(n) time to find an element because they check each item one by one.
- Hence, dictionaries are more efficient for key-based data retrieval.

## 4. How are Python strings immutable if they allow operations like replace()?
- Strings in Python are immutable, meaning their content can’t be changed after creation.
- When you use methods like replace(), Python returns a new string object instead of modifying the original.
- This behavior preserves the immutability property.
```python
s = "hello"
print(s.replace("h", "y"))  # Output:"yello"
print(s)  # Output: "hello"
```

## 5. How do you merge two dictionaries in the latest Python version?
- In Python latest version, dictionaries can be merged using the '|' operator.
- This creates a new dictionary that combines the key-value pairs of both dictionaries.
- If there are duplicate keys, values from the right-hand dictionary take priority.
```python
dict1 = {'a': 1}
dict2 = {'b': 2}
merged = dict1 | dict2
print(merged)  # Output: {'a': 1, 'b': 2}
```

## 6. Explain dictionary comprehension with example?
- Dictionary comprehension is a concise way to create dictionaries from iterable data.
- It follows the format {key: value for item in iterable}.
- This makes it easier to generate mappings programmatically, like squares of numbers.
```python
squares = {x: x**2 for x in range(5)}
print(squares)  # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

## 7. What are nested dictionaries and how do you access inner values?
- A nested dictionary contains another dictionary as a value for one or more keys.
- You can access inner values by chaining keys, like dict['outer']['inner'].
- It is commonly used to store structured or hierarchical data.
```python
data = {'student': {'name': 'John', 'age': 20}}
print(data['student']['name'])  # Output: John
```

## 8. How can you convert a list of tuples into a dictionary?
- A list of tuples, where each tuple is a key-value pair, can be converted using the dict() constructor.
- This is a quick way to transform structured data into dictionary format.
- Each tuple must have exactly two elements.
```python
l = [('a', 1), ('b', 2)]
d = dict(l)
print(d)  # Output: {'a': 1, 'b': 2}
```

## 9. How would you handle missing keys in a dictionary?
- Use the get() method to safely access keys and provide a default value if the key is missing.
- Alternatively, use collections.defaultdict for automatic default values.
- This prevents KeyError exceptions.
```python
d = {'a': 1}
print(d.get('b', 0))  # Output: 0
```

## 10. Can we use a list as a key in a dictionary? Why/Why not?
- No, lists are mutable and cannot be used as dictionary keys.
- Dictionary keys must be immutable and hashable, like strings, numbers, or tuples.
- Using a list will result in a TypeError.

## 11. What happens if you try to add a mutable object to a set?
- Sets only allow hashable (immutable) elements.
- Trying to add a mutable object like a list results in a TypeError.
- This ensures that set elements remain unique and consistent.

## 12. write a code to find common elements in two lists using set operations?
- You can use the intersection & operator between two sets to find common elements.
- This is efficient and concise compared to manual looping.
- The result is a set of elements that exist in both lists.
```python
list1 = [1, 2, 3]
list2 = [2, 3, 4]
common = set(list1) & set(list2)
print(list(common))  # Output: [2, 3]
```

## 13. what is the difference between is and == for string ? what is the syntax?
- == compares the values of two variables, while is checks whether they refer to the same object in memory.
- For immutable types like strings, both may return True for identical values.
- However, their behavior differs in other contexts.
```python
a = "hello"
b = "hello"
print(a == b)  # Output: True
print(a is b)  # Output: True 
```

## 14. How does slicing work in tuples and strings? what is the Syntax?
- Slicing extracts a portion of a sequence using [start:end] or [start:end:step] syntax.
- It works on strings, lists, and tuples.
- Negative indices and steps allow reverse or skip-based slicing.
```python
s = "Python"
t = (1, 2, 3, 4)
print(s[1:4])  # Output: "yth"
print(t[:2])   # Output: (1, 2)
```

## 15. How can you reverse a string or list using slicing?
- You can reverse any sequence using slicing with a step of -1, like [::-1].
- This returns a new reversed sequence without modifying the original.
- It’s a Pythonic way to reverse strings and lists efficiently.
```python
s = "hello"
l = [1, 2, 3]
print(s[::-1])    # Output: "olleh"
print(l[::-1])  # Output: [3, 2, 1]
```

## 16. How would you optimize a recursive function to avoid maximum recursion depth errors in Python?
- Recursive functions in Python can hit a recursion depth limit, causing a RecursionError.
- To avoid this, use memoization or convert the recursive logic into an iterative form.
- Memoization caches results and prevents repeated computation.
```python
# Optimized Recursive Function Using Memoization:
def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
    return memo[n]

# Ex:
print(fibonacci(10))  # Output: 55
print(fibonacci(50))  # Output: 12586269025

# Explanation:
- memo={}: A default dictionary used to cache previously computed Fibonacci numbers.
  if n in memo: Checks if the result is already cached to skip redundant computation.
  Handles very large inputs (e.g., fibonacci(1000)) more efficiently than naive recursion.
```
```python
# Optimized Recursive Function Using Iteration (No Recursion):
def fibonacci_iterative(n):
    if n <= 1:
        return n
    a, b = 0, 1
    for _ in range(2, n + 1):
        a, b = b, a + b
    return b

# Ex:
print(fibonacci_iterative(10))  # Output: 55
print(fibonacci_iterative(50))  # Output: 12586269025

# Ex:
This avoids recursion entirely by using a loop, so there's no risk of hitting the recursion depth limit.
It’s also more memory-efficient and faster for large n, especially compared to naive recursion.
It maintains the same logic flow as the recursive Fibonacci sequence but in a stack-safe and performance-optimized form.
```
