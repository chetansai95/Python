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
<pre> ```a = [1, 2, 2, 3]  unique = list(set(a))  # [1, 2, 3] ``` </pre>


