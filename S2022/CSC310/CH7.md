# Space and Time Tradeoffs

Two varieties of space for time algorithms:
- input enhancement
- prestructuring: preprocess input to make accessing elements easier

## Comparison-Counting Sort
- Given an array of values
- Create a second array that holds the number of elements smaller than the element at the corresponding position in the original array

---
## Hashing
- A very efficient method for implementing a *dictionary*, a set with the operations:
  - Find
  - Insert
  - Delete
- Based on representation-change and space-for-time tradeoff ideas
- Important applications:
  - Symbol tables
  - Databases (*extendible hashing*)

The idea of hashing is to map keys of a given file of size `n` into a table of size `m`, called the hash table, by using a predefined function, called the *hash function.*
```
h: K -> location(cell) in the hash table
```

Example: student records, key = SSN. Hash function:
```
h(k) = k % m where m is some integer (typically prime)
```
If `m` = 1000, where is record with `SSN = 314158265` stored?

## Collisions
If *h*(*K*<sub>1</sub>) = *h*(*K*<sub>2</sub>), there is a collision
- Good hash functions result in fewer collisions but some collisions should be expected (*birthday paradox*)
- Two principal hashing schemes handle collisions differently
  - *Open hashing*
    - Each cell is a header of linked list of all keys hashed to it
  - *Closed hashing*
    - One key per cell
    - In case of collision, finds another cell by
      - Linear probing: use next free bucket
      - Double hashing: use second hash function to compute increment

## Open hashing (Separate chaining)
Keys are stored in linked lists *outside* a hash table whose elements serve as the lists' headers.

(**PPT**): Example:  `A, FOOL, AND, HIS, MONEY, ARE, SOON, PARTED`

  - *h*(*K*) = sum of *K*'s letters' positions in the alphabet `MOD 13`

If hash function distributes keys uniformly, average length of linked list will be *a* = *n/m.* This ratio is called **load factor.**