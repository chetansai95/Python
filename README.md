# Python

### 1. Difference between List and Tuple in Python?
| Feature     | List                       | Tuple             |
| ----------- | -------------------------- | ----------------- |
| Mutability  | Mutable                    | Immutable         |
| Syntax      | `[]`                       | `()`              |
| Performance | Slower (due to mutability) | Faster            |
| Use Case    | Dynamic data               | Fixed/static data |


### 2. How do sets help in removing duplicates from a list?
A set automatically removes duplicates because it only allows unique elements.  
```python
a = [1, 2, 2, 3]
unique = list(set(a))
print(unique)  # Output: [1, 2, 3]
```

### 3. Why are dictionaries faster than lists for lookups?
- Dictionaries use a hash table, which allows O(1) time complexity for lookups.
- Lists require O(n) time to search because they don’t use keys or hashing.




