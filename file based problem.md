Sure, I can provide more advanced and interview-level questions based on the topics we've covered so far: Reading and Writing Files and Context Managers.

### Advanced Interview-Level Questions

#### Multiple Choice Questions

1. What will be the output of the following code snippet?

```python
with open("example.txt", "w") as file:
    file.write("Hello, world!")
    file.writelines(["\nLine 1", "\nLine 2", "\nLine 3"])

with open("example.txt", "r") as file:
    data = file.readlines()

print(data)
```

A. `['Hello, world!\\n', 'Line 1\\n', 'Line 2\\n', 'Line 3\\n']`
B. `['Hello, world!', 'Line 1', 'Line 2', 'Line 3']`
C. `['Hello, world!', '\\nLine 1', '\\nLine 2', '\\nLine 3']`
D. `['Hello, world!', 'Line 1\\nLine 2\\nLine 3']`

2. Consider the following code:

```python
def process_file(filename):
    with open(filename, 'r') as file:
        for line in file:
            yield line.strip()

lines = process_file('example.txt')
for line in lines:
    print(line)
```

What is the primary benefit of using a generator function (`yield`) in this context?

A. It simplifies the code.
B. It reads the entire file into memory at once.
C. It allows for lazy evaluation, processing one line at a time.
D. It makes the code run faster.

3. Given the code snippet below, what will be the result of running it?

```python
with open("example.txt", "w") as file:
    file.write("First line\n")
    raise Exception("An error occurred!")
    file.write("Second line\n")

with open("example.txt", "r") as file:
    print(file.read())
```

A. Only "First line\n" will be written to the file.
B. "First line\nSecond line\n" will be written to the file.
C. The file will be empty because of the exception.
D. "An error occurred!" will be written to the file.

4. What does the following code snippet do?

```python
with open("example.txt", "w") as file:
    file.write("Test line")
```

A. It reads the file "example.txt".
B. It appends "Test line" to "example.txt".
C. It writes "Test line" to a new file "example.txt" or truncates it if it already exists.
D. It opens "example.txt" in read mode.

5. Consider the following code:

```python
def read_large_file(file_path):
    with open(file_path, 'r') as file:
        while True:
            data = file.read(1024)
            if not data:
                break
            yield data

for chunk in read_large_file('large_file.txt'):
    print(chunk)
```

What is the primary advantage of this approach?

A. It reads the entire file into memory at once.
B. It allows processing large files in smaller chunks, reducing memory usage.
C. It makes the code more complex but efficient.
D. It ensures the file is closed automatically after reading.

#### Programming Questions

1. **Problem**: Write a Python function that reads a file containing a list of numbers (one number per line), sorts them in ascending order, and writes the sorted numbers to a new file.

```python
def sort_numbers(input_file, output_file):
    # Your code here
    pass

# Example usage:
sort_numbers('numbers.txt', 'sorted_numbers.txt')
```

2. **Problem**: Create a context manager that temporarily changes the working directory and then reverts to the original directory after the block inside the `with` statement is executed.

```python
import os

class ChangeDirectory:
    def __init__(self, new_path):
        self.new_path = new_path
        self.old_path = os.getcwd()

    def __enter__(self):
        os.chdir(self.new_path)

    def __exit__(self, exc_type, exc_value, traceback):
        os.chdir(self.old_path)

# Example usage:
with ChangeDirectory('/path/to/new/directory'):
    # Perform operations in the new directory
    pass
# Back to the original directory
```

3. **Problem**: Implement a function that merges two text files line by line. If one file is shorter, append the remaining lines of the longer file to the result.

```python
def merge_files(file1, file2, output_file):
    # Your code here
    pass

# Example usage:
merge_files('file1.txt', 'file2.txt', 'merged.txt')
```

4. **Problem**: Write a Python function that reads a text file and counts the frequency of each word, then writes the word frequencies to a new file in the format: "word: frequency".

```python
def word_frequency(input_file, output_file):
    # Your code here
    pass

# Example usage:
word_frequency('example.txt', 'word_freq.txt')
```

Try solving these questions to solidify your understanding of file handling and context managers. Let me know if you need any clarifications or further explanations!
