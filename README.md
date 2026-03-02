Lab-4b-Dictionary-GRADED-LAB-

Joshua Vega
CISC 179
 ```python
 ## Dictionary with 10 key-value pairs

car_info = {
    "brand": "Dodge",
    "model": "Charger",
    "year": 2015,
    "engine": "V6",
    "color": "Black",
    "miles": 92000,
    "transmission": "Automatic",
    "owner": "Joshua",
    "country": "USA",
    "status": "Stock"
}

print(car_info)
print("Model:", car_info["model"])
print("Year:", car_info["year"])

 ```
## Take user input and add into dictionary
 ##We need 2 keys: SSN and Name
 ```python
 my_user_dict = {}

continue_input = "Y"

while continue_input == "Y":
    ssn = input("Enter SSN: ")
    name = input("Enter Name: ")

    my_user_dict[ssn] = name

    continue_input = input("Do you want to continue (Y/N): ")

print(my_user_dict)
print("Total keys:", len(my_user_dict))
 ```
 Converting tuples into dictionary
 ```python
 a = [("a", 1), ("b", 2), ("c", 3)]

res = dict(a)

print(res)

 ```

 ## Validate key value pairs and check duplication
 
 ```python
data = [
    ('Name', 'jose manuel'),
    ('Date of birth', '1 Jan 1980'),
    ('Address', '1000 Black Mountain Drive'),
    ('Name', 'Josh')
]
validated_dict = {}

for item in data:
    

    if len(item) != 2:
        print("Invalid key-value pair:", item)
    else:
        key = item[0]
        value = item[1]

        if key in validated_dict:
            print("Duplicate key found:", key)
            new_key = input("Please enter a new key name: ")
            validated_dict[new_key] = value
        else:
            validated_dict[key] = value

print(validated_dict)

 ```

## Convert list into dictionary using loop
```python
tuple_list = [("x", 10), ("y", 20), ("z", 30)]

new_dict = {}

for pair in tuple_list:
    key = pair[0]
    value = pair[1]
    new_dict[key] = value

print(new_dict)

```
```python
## Count words using dictionary

text = """The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia.
It has a powerful muscular body with a large head and paws, a long tail and orange fur with black,
mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some
recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands."""

## Remove punctuation
text = text.replace("(", "")
text = text.replace(")", "")
text = text.replace(",", "")
text = text.replace(".", "")

words = text.split()

word_count = {}

for word in words:
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

print(word_count)
print("Total unique words:", len(word_count))
```

## Troubleshooting
```python
# Problem: assigning creates a reference, not a copy

d_orig = {123: "Coconut"}

d_copy = d_orig   # this does NOT create a new dictionary

d_copy[456] = "Mango"

print("Original after change:", d_orig)
print("Copy:", d_copy)
```


```python
d_orig = {123: "Coconut"}

d_copy = d_orig.copy()

d_copy[456] = "Mango"

print("Original:", d_orig)
print("Copy:", d_copy)

```

## Solution explanation
The problem happens because
d_copy = d_orig
This does not create a new dictionary. It just creates another reference to the same memory.
Solution:

```python
d_copy = d_orig.copy()
```

## This creates a new independent dictionary.
TypeError: unhashable type: 'list'

```python
my_dict = {}

key = [1, 2, 3]   # list

my_dict[key] = "Test"
```
Lists are mutable, and dictionary keys must be immutable like strings, numbers, or tuple.
Since lists can change, Python cannot hash them, so it raises:
TypeError: unhashable type: 'list'

Challenges
One challenge was remembering that dictionaries do not allow duplicate keys.
Another challenge was understanding that assigning one dictionary to another does not create a copy but a reference.
