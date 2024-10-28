
#### For `blog_id_6.md` (Dictionaries)

```markdown
# Understanding Dictionaries in Python

## Introduction
Dictionaries are a built-in data type in Python that store key-value pairs. They are useful for associating values with unique keys, allowing for fast retrieval of data.

## How Dictionaries Work
Dictionaries consist of:
- **Keys**: Unique identifiers used to access values.
- **Values**: Data associated with each key, which can be of any data type.

## Example
Here’s an example of creating and accessing a dictionary:

```python
student = {
    "name": "John Doe",
    "age": 21,
    "courses": ["Math", "Science"]
}

print(student["name"])  # Output: John Doe
print(student.get("age"))  # Output: 21
