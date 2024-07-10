Let's review your answers and solutions:

### Review of MCQs

1. **Correct Answer**: A
   - Your Answer: A
   - Explanation: The code writes "Hello, world!" followed by three new lines each starting with "Line 1", "Line 2", and "Line 3". Hence, the output will be `['Hello, world!\n', 'Line 1\n', 'Line 2\n', 'Line 3\n']`.

2. **Correct Answer**: C
   - Your Answer: B
   - Explanation: Using a generator (`yield`) allows for lazy evaluation, processing one line at a time, which is efficient for large files. It does not read the entire file into memory.

3. **Correct Answer**: A
   - Your Answer: B
   - Explanation: The file will only have "First line\n" because the `Exception` is raised before the second `write` statement is executed. The `with` statement ensures that the file is properly closed even if an exception occurs.

4. **Correct Answer**: C
   - Your Answer: B
   - Explanation: The `open` function with "w" mode writes "Test line" to a new file "example.txt" or truncates it if it already exists.

5. **Correct Answer**: B
   - Your Answer: B
   - Explanation: The code processes large files in smaller chunks (1024 bytes at a time), reducing memory usage.

### Review of Programming Questions

6. **Correct Answer**: Your solution is correct.
   ```python
   def sort_numbers(input_file, output_file):
       with open(input_file, 'r') as src, open(output_file, 'w') as dst:
           numbers = sorted([int(line.strip()) for line in src])
           for number in numbers:
               dst.write(f"{number}\n")
   
   # Example usage:
   sort_numbers('example.txt', 'destination.txt')
   ```

   - The function reads the numbers from `input_file`, sorts them, and writes them to `output_file`.

### Additional Programming Questions

Here are some more advanced programming questions to practice on the topics of reading and writing files and using context managers:

1. **Problem**: Write a Python function that reads a CSV file, sorts the rows by a specific column, and writes the sorted rows to a new CSV file. Assume the first row contains headers.

```python
import csv

def sort_csv(input_file, output_file, sort_column):
    with open(input_file, 'r') as src, open(output_file, 'w', newline='') as dst:
        reader = csv.reader(src)
        writer = csv.writer(dst)
        
        header = next(reader)
        writer.writerow(header)
        
        rows = sorted(reader, key=lambda row: row[sort_column])
        writer.writerows(rows)

# Example usage:
sort_csv('example.csv', 'sorted.csv', 1)  # Sort by the second column
```

2. **Problem**: Create a context manager that logs the execution time of a block of code.

```python
import time

class ExecutionTimer:
    def __enter__(self):
        self.start_time = time.time()
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        end_time = time.time()
        elapsed_time = end_time - self.start_time
        print(f"Elapsed time: {elapsed_time:.2f} seconds")

# Example usage:
with ExecutionTimer():
    # Your code here
    time.sleep(2)
```

3. **Problem**: Write a Python function that merges multiple text files into one, with each file's content separated by a specified delimiter.

```python
def merge_files_with_delimiter(file_list, output_file, delimiter="\n"):
    with open(output_file, 'w') as dst:
        for file_name in file_list:
            with open(file_name, 'r') as src:
                dst.write(src.read())
                dst.write(delimiter)

# Example usage:
merge_files_with_delimiter(['file1.txt', 'file2.txt', 'file3.txt'], 'merged.txt', delimiter="\n---\n")
```

4. **Problem**: Write a Python function that reads a text file and replaces all occurrences of a specific word with another word, then writes the result to a new file.

```python
def replace_word_in_file(input_file, output_file, old_word, new_word):
    with open(input_file, 'r') as src, open(output_file, 'w') as dst:
        for line in src:
            dst.write(line.replace(old_word, new_word))

# Example usage:
replace_word_in_file('example.txt', 'replaced.txt', 'old', 'new')
```

5. **Problem**: Implement a context manager that temporarily changes the environment variables within its context and reverts them back after the context block is executed.

```python
import os

class TemporaryEnvVar:
    def __init__(self, var_name, new_value):
        self.var_name = var_name
        self.new_value = new_value
        self.old_value = os.getenv(var_name)
        
    def __enter__(self):
        os.environ[self.var_name] = self.new_value
        
    def __exit__(self, exc_type, exc_value, traceback):
        if self.old_value is None:
            del os.environ[self.var_name]
        else:
            os.environ[self.var_name] = self.old_value

# Example usage:
with TemporaryEnvVar('MY_VAR', 'new_value'):
    print(os.getenv('MY_VAR'))  # Output: new_value
print(os.getenv('MY_VAR'))  # Output: None (or the previous value)
```

Try solving these problems to deepen your understanding and practice. Let me know if you need further assistance or explanations!
