### Advanced Python Interview Questions (MCQs and Problems)

#### MCQs

1. **Which of the following is true about Python's `with` statement?**
    - A) It is used to handle exceptions.
    - B) It ensures that resources are properly released.
    - C) It is used to create lambda functions.
    - D) It is used to define classes.

2. **What will be the output of the following code?**
    ```python
    def func(x=[]):
        x.append(1)
        return x

    print(func())
    print(func())
    ```
    - A) `[1] [1]`
    - B) `[1] [1, 1]`
    - C) `[1, 1] [1]`
    - D) `[1] [1] [1] [1]`

3. **Which of the following is used to create a new instance of a class in Python?**
    - A) `class()`
    - B) `new()`
    - C) `__init__`
    - D) `__new__`

4. **What does the `setdefault()` method in dictionaries do?**
    - A) Returns a value for a key and removes it from the dictionary.
    - B) Updates the dictionary with the specified key-value pair.
    - C) Returns the value of the specified key. If the key does not exist, inserts the key with a specified value.
    - D) Removes all items from the dictionary.

5. **What will be the output of the following code?**
    ```python
    class A:
        def __init__(self):
            self.x = 1
        def change(self):
            self.x += 1

    class B(A):
        def __init__(self):
            super().__init__()
            self.y = 1
        def change(self):
            self.x += 1
            self.y += 1

    obj = B()
    obj.change()
    print(obj.x, obj.y)
    ```
    - A) `1 1`
    - B) `2 2`
    - C) `2 1`
    - D) `1 2`

#### Problems

1. **Problem: Find the Longest Substring Without Repeating Characters**
   Write a function that takes a string and returns the length of the longest substring without repeating characters.
   ```python
   def length_of_longest_substring(s: str) -> int:
       pass

   # Example usage:
   print(length_of_longest_substring("abcabcbb"))  # Output: 3
   print(length_of_longest_substring("bbbbb"))     # Output: 1
   print(length_of_longest_substring("pwwkew"))    # Output: 3
   ```

2. **Problem: Flatten a Nested List**
   Write a function that takes a nested list and returns a flat list.
   ```python
   def flatten(nested_list):
       pass

   # Example usage:
   nested_list = [1, [2, [3, 4], 5], 6, [7, 8]]
   print(flatten(nested_list))  # Output: [1, 2, 3, 4, 5, 6, 7, 8]
   ```

3. **Problem: Find the Median of Two Sorted Arrays**
   Write a function that takes two sorted arrays and returns the median of the two sorted arrays.
   ```python
   def find_median_sorted_arrays(nums1, nums2):
       pass

   # Example usage:
   nums1 = [1, 3]
   nums2 = [2]
   print(find_median_sorted_arrays(nums1, nums2))  # Output: 2.0

   nums1 = [1, 2]
   nums2 = [3, 4]
   print(find_median_sorted_arrays(nums1, nums2))  # Output: 2.5
   ```

4. **Problem: Group Anagrams**
   Write a function that takes a list of strings and groups anagrams together.
   ```python
   def group_anagrams(strs):
       pass

   # Example usage:
   strs = ["eat", "tea", "tan", "ate", "nat", "bat"]
   print(group_anagrams(strs))
   # Output: [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
   ```

5. **Problem: Implement a Cache with LRU (Least Recently Used) Eviction Policy**
   Implement a class `LRUCache` that simulates a cache with LRU eviction policy. It should support `get` and `put` operations.
   ```python
   class LRUCache:
       def __init__(self, capacity: int):
           pass

       def get(self, key: int) -> int:
           pass

       def put(self, key: int, value: int) -> None:
           pass

   # Example usage:
   cache = LRUCache(2)
   cache.put(1, 1)
   cache.put(2, 2)
   print(cache.get(1))       # Output: 1
   cache.put(3, 3)
   print(cache.get(2))       # Output: -1
   cache.put(4, 4)
   print(cache.get(1))       # Output: -1
   print(cache.get(3))       # Output: 3
   print(cache.get(4))       # Output: 4
   ```

### Instructions
1. Answer the MCQs.
2. Solve the problems.
3. Submit your answers and solutions for review.
