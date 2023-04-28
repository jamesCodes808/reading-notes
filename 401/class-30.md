# Hash Tables

## WHY WHAT HOW

## WHY: 

Hash tables are used because they are:
- Fast and efficient with space time complexity cases when using basic operations (insert, deletes, search)
- Great when storing data with key-value pairs or dictionary objects
- Able to hold various kinds of data types as unique keys

## WHAT:
Hash tables are a data structure used to efficiently store and retrieve key-value pairs. 

Two main components:
- Key: i.e. "Name"

- Value: i.e. phone #

Utilizing key-value pairs, each `Node` or `Bucket` in a HashTable will have a key and a value.

The `Buckets` are contained in each index of the array in a hashtable. Each index essentially, IS a `bucket`. Sometimes these index/buckets can contain multiple key-value pairs.


```python
sample = [{'bob': 1231234123}, {'linda': 32132146542}, {'tina': 3219876545}, {'louise': 6549878654}, {'gene': 6547896395}]

```

Through a `hash` HashTables are able to store keys and retrieve the value for that key in a quick manner. 

`Hash` is the ability to encode a key that will map to a specific location in an associative array. That location can easily be looked up to retrieve the value that belongs to that key, making search operations fast and efficient. 

The process of Hashing is predictable and will always turn the same key into the same integer hash code.

A simple algorithm that is used to `hash` a key for index placement is:
1. Add or multiply all the ASCII values together.
2. Multiply it by a prime number such as 599.
3. Use modulo to get the remainder of the result, when divided by the total size of the array.
4. Insert into the array at that index.

```python
sample = {'bob': 1231234123,
        'linda': 32132146542,
        'tina': 3219876545,
        'louise': 6549878654,
        'gene': 6547896395}

def hash(key):
    # ...put hash function here that spit out the same index

# when we run Hash function on a certain key
hash('bob')
# we will always print out the same index 
# hash('bob') -> 3
# in the hash table the key to 'bob' now lives at 3 
# hash_table = [0,1,2,'hashed_bob_key']

# same happens if we hash another key
hash('linda')
# hash('linda') -> 1
# hash_table = [0,'hashed_linda_key',2,'hashed_bob_key']
```

Sometimes, hashing can create the same hash index in the hash table from a different key, this is called a `collision`.

These `collisions` can be handled in several ways:

- Separate Chaining(Open Hashing): 
In this method, each index in the hash table holds a linked list of key-value pairs that hashed to that index. When a collision occurs, the new key-value pair is simply added to the end of the linked list at that index.

- Linear Probing(Open Addressing/Closed Hashing)
 In this method, when a collision occurs, a new index is calculated using a probe sequence that depends on the original hash index. There are several ways to define the probe sequence, including linear probing, quadratic probing, and double hashing.

Most HashTables will have these basic methods:

- `set()`: Adds a key-value pair to a hash table or updates the value of an existing key.
- `get()`: Retrieves the value associated with a given key from a hash table.
- `has()`: Returns a boolean indicating whether a given key is present in a hash table.
- `keys()`: Returns a list of all keys present in a hash table.
- `hash()`: Returns the hash value of a given object.

## HOW:

This is how we would set up a basic `HashTable`:

```python
class HashTable:
    def __init__(self, size):
        self.size = size
        self.table = [None] * size

    def _hash(self, key):
        # Hash function that maps a key to an index in the hash table
        # (i.e., using the algorithm mentioned earlier)
        return hash(key) % self.size

    def set(self, key, value):
        # Store a key-value pair in the hash table
        index = self._hash(key)
        self.table[index] = value

    def get(self, key):
        # Retrieve the value associated with a key from the hash table
        index = self._hash(key)
        return self.table[index]

    def has(self, key):
        # Check if a key is present in the hash table
        index = self._hash(key)
        return self.table[index] is not None

    def keys(self):
        # Return a list of all keys in the hash table
        return [key for key, value in enumerate(self.table) if value is not None]

```

## Things I want to know more about

> References
>
>[Intro to Hashtables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)
>
>[What is a HashTable - Video](https://www.youtube.com/watch?v=MfhjkfocRR0)
>
>[Basics of Hash Tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)
>
>[Hash Table Wiki](https://en.wikipedia.org/wiki/Hash_table)