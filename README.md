# Python-Tricky-Cheatsheet
This repository contains a set of tricky Python interview questions with explanations to help you understand and prepare for Python interviews.

## Question 1: List Mutability
```python
a = [1, 2, 3]
b = a  # Both `a` and `b` point to the same list
b.append(4)  # Modifies the shared list
print(a)  # Output: [1, 2, 3, 4]
print(b)  # Output: [1, 2, 3, 4]
```
**Explanation**: `a` and `b` refer to the same list object, so changes to one affect the other.

---

## Question 2: Global Variables
```python
x = 10

def modify_var():
    global x
    x += 5  # Modify the global variable

modify_var()
print(x)  # Output: 15
```
**Explanation**: The `global` keyword allows modification of the global variable `x` within the function.

---

## Question 3: Slicing Out-of-Bounds
```python
list = ['a', 'b', 'c', 'd', 'e']
print(list[10:])  # Output: []
```
**Explanation**: Python slicing does not raise an error if the start index is out of range; it returns an empty list.

---

## Question 4: Mutable Lists
```python
list = [[]] * 5
print(list)  # Output: [[], [], [], [], []]
list[0].append(10)
print(list)  # Output: [[10], [10], [10], [10], [10]]
list[1].append(20)
print(list)  # Output: [[10, 20], [10, 20], [10, 20], [10, 20], [10, 20]]
list.append(30)
print(list)  # Output: [[10, 20], [10, 20], [10, 20], [10, 20], [10, 20], 30]
```
**Explanation**: `list = [[]] * 5` creates five references to the same inner list. Changes to one reflect in all.

---

## Question 5: String Operations
```python
def main(a):
    a = a + '2'
    a = a * 2
    return a

print(main("byte"))  # Output: byte2byte2
```
**Explanation**: Strings are concatenated and repeated using `+` and `*` operators, respectively.

---

## Question 6: Infinite Loop with Break
```python
i = 1
while True:
    if i % 3 == 0:
        break
    print(i)  # Output: 1, 2
    i += 1
```
**Explanation**: The loop breaks when `i` becomes divisible by 3.

---

## Question 7: Min-Max Operations
```python
ans = min(max(False, -7.5, -7), 2, 1, 9)
print(ans)  # Output: 1
```
**Explanation**: `False` is treated as 0; the `max` function evaluates `0, -7.5, -7` to 0, and `min(0, 2, 1, 9)` gives 1.

---

## Question 8: List Comprehension
```python
text = 'hello world'
x = [i for i in text if i not in "aeiou"]
print(x)  # Output: ['h', 'l', 'l', ' ', 'w', 'r', 'l', 'd']
```
**Explanation**: The comprehension filters out vowels from the string.

---

## Question 9: Dictionary Default Value
```python
d = {1: "A", 2: "B", 3: "C"}
print(d.get(1, 4))  # Output: A
```
**Explanation**: `dict.get(key, default)` returns the value for the key if it exists, otherwise the default value.

---

## Question 10: Exponentiation Precedence
```python
print(2**(3**2))  # Output: 512
print((2**3)**2)  # Output: 64
print(2**3**2)    # Output: 512
```
**Explanation**: Exponentiation is right-associative in Python.

---

## Question 11: `is` Operator
```python
a = 10
b = 10.0
c = "10"
print(a is b)        # Output: False
print(a is int(b))   # Output: True
print(c is str(a))   # Output: False
```
**Explanation**: `is` checks for identity, not equality. Integer conversion makes `int(b)` identical to `a`.

---

## Question 12: Boolean Arithmetic
```python
a = True  # Equivalent to 1
b = False # Equivalent to 0
print(a + 1)  # Output: 2
print(b * 10) # Output: 0
```
**Explanation**: Boolean values are treated as integers in arithmetic operations.

---

## Question 13: String Indexing and Slicing
```python
string = "interview"
print(string[0:5])  # Output: inter
print(string[::-1]) # Output: weivretni
```
**Explanation**: Slicing extracts substrings, and `[::-1]` reverses the string.

---

## Question 14: List Comprehension with Squares
```python
numbers = [x**2 for x in range(5)]
print(numbers)  # Output: [0, 1, 4, 9, 16]
```
**Explanation**: The comprehension squares numbers from 0 to 4.

---

## Question 15: Set Operations
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
print(set1 & set2)  # Output: {3}
print(set1 | set2)  # Output: {1, 2, 3, 4, 5}
```
**Explanation**: `&` computes intersection, and `|` computes union of sets.

---

## Question 16: List Methods
```python
lst = [1, 2, 3]
lst.append(4)
lst.insert(1, 5)
lst.pop()
print(lst)  # Output: [1, 5, 2, 3]
```
**Explanation**: Demonstrates `append`, `insert`, and `pop` methods on lists.

---

## Question 17: String Multiplication
```python
s = "Python"
print(s[:3] * 2)  # Output: PytPyt
```
**Explanation**: `s[:3]` extracts the first three characters, and `* 2` repeats them.

---

## Question 18: Set Comprehension
```python
nums = [1, 2, 2, 3, 4, 4]
unique_squares = {x**2 for x in nums}
print(unique_squares)  # Output: {1, 4, 9, 16}
```
**Explanation**: Set comprehensions eliminate duplicates automatically.

## Question 19: Shallow and Deep Copy
```
import copy
arr = [[1, 2, 3], [4, 5, 6]]
shallow_copied = copy.copy(arr)
deep_copied = copy.deepcopy(arr)
arr[1][1] = 100

print("Original list after modification:", arr)
print("Shallow copy:", shallow_copied)
print("Deep copy:", deep_copied)
```
**Explanation**: Shallow Copy: Copies the outer structure but not the nested objects.
                 Deep Copy: Creates a fully independent copy, including all nested objects.
                 
## Question 20: List Comprehension with Conditional Expression
```
result = [x if x % 2 == 0 else x * 2 for x in range(5)] 
print(result)  #Output: [0,2,2,6,4]

```
**Explanation**: For each number in the range, if it's even, it's added to the list as-is; if it's odd, it's multiplied by 2 before adding.


### Question 21: What is the purpose of the `zip` function?

The `zip` function in Python combines two or more iterables (e.g., lists or tuples) element-wise into tuples. The resulting tuples contain one element from each of the iterables, up to the shortest iterable's length.

#### Example:
```python
a = [1, 2, 3, 4]
b = ['a', 'b', 'c', 'd']
zipped = []
for i in zip(a, b):
    zipped.append(i)
print(zipped)
```

#### Output:
```
[(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd')]
```

**Explanation:**
- The `zip` function pairs the elements from `a` and `b` to form tuples.
- The `zipped` list contains these tuples.

---

### Question 22: How do you merge two dictionaries in Python?

Starting from Python 3.9, you can merge dictionaries using the `|` operator.

#### Example:
```python
dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 1, 'd': 5}
merged = dict1 | dict2
print(merged)
```

#### Output:
```
{'a': 1, 'b': 2, 'c': 1, 'd': 5}
```

**Explanation:**
- The `|` operator creates a new dictionary by combining the key-value pairs of `dict1` and `dict2`.
- If both dictionaries have the same key, the value from the second dictionary overrides the value from the first.

#### Note:
For Python versions below 3.9, you can use the `update` method or dictionary unpacking to achieve the same result:

```python
dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 1, 'd': 5}
# Using update method
dict1.update(dict2)
print(dict1)

# Using dictionary unpacking
merged = {**dict1, **dict2}
print(merged)
```

## Question 22: Sort the dictionary based on the values

You can sort a dictionary based on its values or keys using the `sorted` function with a custom `key` argument.

#### Example:
```python
obj = {
    'a': 1,
    'b': 5,
    'c': 4,
    'd': 10,
    'e': 8
}
sort_dict_values = dict(sorted(obj.items(), key=lambda item: item[1]))
sort_dict_keys = dict(sorted(obj.items(), key=lambda item: item[0]))

print(sort_dict_values)
print(sort_dict_keys)
```

#### Output:
```
{'a': 1, 'c': 4, 'b': 5, 'e': 8, 'd': 10}
{'a': 1, 'b': 5, 'c': 4, 'd': 10, 'e': 8}
```

**Explanation:**
- `sorted(obj.items(), key=lambda item: item[1])` sorts the dictionary by values in ascending order.
- `sorted(obj.items(), key=lambda item: item[0])` sorts the dictionary by keys in ascending order.
- The `dict()` constructor converts the sorted items back into a dictionary.

---


