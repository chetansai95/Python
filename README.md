# Python Interview Questions

## 1. Difference between List and Tuple in Python?
| Feature     | List                       | Tuple             |
| ----------- | -------------------------- | ----------------- |
| Mutability  | Mutable                    | Immutable         |
| Syntax      | `[]`                       | `()`              |
| Performance | Slower (due to mutability) | Faster            |
| Use Case    | Dynamic data               | Fixed/static data |  


## 2. How do sets help in removing duplicates from a list?
A set automatically removes duplicates because it only allows unique elements.  
```python
a = [1, 2, 2, 3]
unique = list(set(a))
print(unique)  # Output: [1, 2, 3]
```

## 3. Why are dictionaries faster than lists for lookups?
- Dictionaries use a hash table, which allows O(1) time complexity for lookups.
- Lists require O(n) time to search because they don’t use keys or hashing.

## 4. How are Python strings immutable if they allow operations like replace()?
- Operations like replace() return a new string; they don’t modify the original string.
```python
s = "hello"
print(s.replace("h", "y"))  # Output:"yello"
print(s)  # Output: "hello"
```

## 5. How do you merge two dictionaries in the latest Python version?
```python
dict1 = {'a': 1}
dict2 = {'b': 2}
merged = dict1 | dict2
print(merged)  # Output: {'a': 1, 'b': 2}
```

## 6. Explain dictionary comprehension with example?
```python
squares = {x: x**2 for x in range(5)}
print(squares)  # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

## 7. What are nested dictionaries and how do you access inner values?
- A dictionary inside another dictionary.
```python
data = {'student': {'name': 'John', 'age': 20}}
print(data['student']['name'])  # Output: John
```

## 8. How can you convert a list of tuples into a dictionary?
```python
l = [('a', 1), ('b', 2)]
d = dict(l)
print(d)  # Output: {'a': 1, 'b': 2}
```

## 9. How would you handle missing keys in a dictionary?
- Use .get() or defaultdict
```python
d = {'a': 1}
print(d.get('b', 0))  # Output: 0
```

## 10. Can we use a list as a key in a dictionary? Why/Why not?
- No, because lists are mutable and unhashable.
- Dictionary keys must be immutable and hashable types (e.g., str, int, tuple).

## 11. What happens if you try to add a mutable object to a set?
- You'll get a TypeError because sets require elements to be hashable (immutable).

## 12. write a code to find common elements in two lists using set operations?
```python
list1 = [1, 2, 3]
list2 = [2, 3, 4]
common = set(list1) & set(list2)
print(list(common))  # Output: [2, 3]
```

## 13. what is the difference between is and == for string ? what is the syntax?
- is: checks identity (same object in memory)
- ==: checks equality (same content)
```python
a = "hello"
b = "hello"
print(a == b)  # Output: True
print(a is b)  # Output: True 
```

## 14. How does slicing work in tuples and strings? what is the Syntax?
```python
s = "Python"
t = (1, 2, 3, 4)
print(s[1:4])  # Output: "yth"
print(t[:2])   # Output: (1, 2)
```

## 15. How can you reverse a string or list using slicing?
```python
s = "hello"
l = [1, 2, 3]
print(s[::-1])    # Output: "olleh"
print(l[::-1])  # Output: [3, 2, 1]
```
