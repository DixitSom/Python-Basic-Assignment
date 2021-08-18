# Basics of Python

## Introduction

Python is a popular programming language. It was created by Guido van Rossum, and released in 1991.

It is used for:

* web development (server-side),
* software development,
* mathematics,
* system scripting

## Data Types
|          |     |  
 --------- | --- 
 Text Type | ```str```
 Numeric Types | ```int```,```float```,```complex```
 Sequence Types | ```list```, ```tuple```, ```range```
 Mapping Type | ```dict```
 Set Type | ```set```, ```frozenset```
 Boolean Type | ```bool```
 Binary Types | ```bytes```, ```bytesarray```, ```memoryview```

## List

List are the collection of data. List can be used to store hetrogeneous data.

__Syntax:-__
```
mylist = [1, 5, 'Rohan', 10.8, complex('10+5j', True)]
```

### Properties
* List are ordered (means newly added item will be at last)
* Mutable
* Allows Duplicates
* Indexed

### List Methods

Method | Description | Syntax
------ | ----------- | ------
append() | Adds an element at the end of the list | ```mylist.append(item)```
clear() | Removes all the elements from the list | ```mylist.clear()```
count() | Returns the number of elements with the specified value | ```mylist.count(item)```
copy() | Returns a copy of list | ```mylist.copy()```
extend() | Add the elements of a list (or any iterable), to the end of the current list | ```mylist.extend(anotherList())```
index() | Returns the index of the first element with the specified value | ```mylist.index(item)```
insert() | Adds an element at the specified position | ```mylist.insert(position, item)```
pop() | Removes the element at the specified position (from last) | ```mylist.pop()``` *or* ```mylist.pop(index)```
remove() | Removes the item with the specified value | ```mylist.remove(item)```
reverse() | Reverses the order of the list | ```mylist.reverse()```
sort() | Sorts the list | ```mylist.sort()```

## Tuple

Tuples are also collection of data they can store heterogenous data.

__Syntax:-__
```
mytuple = (1, 2, 3, 'This is Tuple')
```
### Properties
* Ordered
* Immutable
* Indexed
* Duplicates Allowed

### Tuple Methods

Method | Description | Syntax
------ | ----------- | ------
count() | Returns the number of times a specified value occurs in a tuple | ```mytuple.count(item)```
index() | Searches the tuple for a specified value and returns the position of where it was found | ```mytuple.index(item)```

## Set

Set are collection data and they can store heterogeneous data.

__Syntax:-__
``` 
myset = {1, 2, 'apple', 'banana'}
```
### Properties
* Unordered
* Unindexed
* Partially mutable (can add or remove items)
* Duplicates are Not allowed

### Set Methods

Method | Description | Syntax
------ | ----------- | ------
add() | Adds an element to the set | ```myset.add(item)```
clear() | Removes all the elements from the set | ```myset.clear()```
copy() | Returns a copy of the set | ```myset.copy()```
difference() | Returns a set containing the difference between two or more sets | ```myset.difference(another_set)```
difference_update() | Removes the items in this set that are also included in another, specified set | ```myset.difference_update(another_set)```
discard() | Remove the specified item | ```myset.discard()```
intersection() | Returns a set, that is the intersection of two other sets | ```myset.intersection(another_set)```
intersection_update() | Removes the items in this set that are not present in other, specified set(s) | ```myset.intersection_update(another_set)```
isdisjoint() | Returns whether two sets have a intersection or not | ```myset.isdisjoint(another_set)```
issubset() | Returns whether another set contains this set or not | ```myset.issubset(another_set)```
issuperset() | Returns whether this set contains another set or not | ```myset.issuperset(another_set)```
pop() | Removes an random element from the set | ```myset.pop()```
remove() | Removes the specified element | ```myset.remove(item)```
symmetric_difference() | Returns a set with the symmetric differences of two sets | ```myset.symmetric_difference(another_set)```
symmetric_difference_update() | inserts the symmetric differences from this set and another | ```myset.symmetric_difference_update()```
union() | Return a set containing the union of sets | ```myset.union(another_set)```
update() | Update the set with the union of this set and others | ```myset.update(another_set)```

## Dictionary

Dictionary is a collection of data. It store data in key-value pairs.

__Syntax:-__
```
mydict = {
    'name': 'Rohan'
    'age': 21
    'loves': 'Movies'
}
```

### Properties
* Ordered
* Mutable
* indexed
* Duplicate Not Allowed (key-value pair)

### Dictionary Methods

Method | Description | Syntax
------ | ----------- | ------
clear() | Removes all the elements from the dictionary | ```mydict.clear()```
copy() | Returns a copy of the dictionary | ```mydict.copy()```
fromkeys() | Returns a dictionary with the specified keys and value | ```mydict.fromkeys(keys, optional-value)```
get() | Returns the value of the specified key | ```mydict.get(key)```
items() | Returns a list containing a tuple for each key value pair | ```mydict.items()```
keys() | Returns a list containing the dictionary's keys | ```mydict.keys()```
pop() | Removes the element with the specified key | ```mydict.pop(key)```
popitem() | Removes the last inserted key-value pair | ```mydict.popitem()```
setdefault() | Returns the value of the specified key. If the key does not exist: insert the key, with the specified value | ```mydict.setdefault(key, value)```
update() | Updates the dictionary with the specified key-value pairs | ```mydict.update(iterable-with-key-value-pair)```
values() | Returns a list of all the values in the dictionary | ```mydict.values()```

## Function

Functions in python are first class objects. And follows following properties.

1. ### Functions are Objects
   ```
   def function(number):
      return number * 50

   print(function(5))
        
   another_Obj = function
        
   print(another_Obj(5))
   ```
   __Output__
   ```
   250
   250
   ```
2. ### Functions can be passed as arguments to other functions
   ```
   def addition(a, b):
      print(a + b)

   def subtraction(a, b):
      print(a - b)

   def starter(func):
      print(f"I am getting function {func.__name__} as an argument")

      func(10, 5)

   starter(addition)
   starter(subtraction)
   ```
   __Output__
   ```
   I am getting function addition as an argument
   15
   I am getting function subtraction as an argument
   5
   ```
3. ### Functions can return another function
   ```
   def multiplier(x):

      def multiply(y):
         return x * y

      return multiply

   multiple_10 = multiplier(10)

   print(multiple_10(5))
   ```
   __Output__
   ```
   50
   ```

## Decorators 

Decorators are used to modify or extend the behaviour of an existing function or class without editing the function or class itself. It allows us to wrap another function to an existing function.

```
def decorator(func):

    def inner(a, b):
        
        if b == 0:
            return "This is not allowed"
        
        ans = func(a, b)

        return ans
    
    return inner

@decorator
def divider(a, b):

    return a / b

print(divider(10, 2))
print(divider(10, 0))
```
__Output__
```
5.0
This is not allowed
```

## Iterators
Iterator is an object that used to iterate through sequencial objects like list, tuple or dictionary.

*\_\_iter\_\_* and *\_\_next\_\_*  are the main functions of an interator object. 

*\_\_iter\_\_* This is calles when a iteration is instantiated then it further calles *\_\_next\_\_* to get next values.

```
ls = [1, 2, 'Rohan', 'c', 10.3]

tp = (1, 2, 3, 4)

dictionary = {1: 'I am good', 2: 'You are also Good'}

print('Iteration through list')

for item in ls:
    print(item)

print('Iteration through tuple')

for item in tp:
    print(item)

print('Iteration through dictionary')

for item in dictionary:
    print(item, ':', dictionary[item])
```

__Output__
```
Iteration through list
1
2
Rohan
c
10.3
Iteration through tuple
1
2
3
4
Iteration through dictionary
1 : I am good
2 : You are also Good
```

Custom Iterator.
```
class Example:

    def __iter__(self):
        self.x = 1

        return self

    def __next__(self):

        x = self.x

        self.x += 1

        return x

iterator = Example()

for i in iterator:
    print(i)

    if i >= 10:
        break

for i in iterator:

    print(i)

    if i >= 10:
        break
```
__Output__
```
1
2
3
4
5
6
7
8
9
10
1
2
3
4
5
6
7
8
9
10
```

__Note:-__ 
## Generators
Generators are iterators. They do not store whole sequence in memory, they generate values on fly.

```
gen = (i * i for i in range(5))

print(gen)

for i in gen:
    print(i)

for i in gen:
    print(i)
```
__Output__
```
<generator object <genexpr> at 0x104ba4660>
0
1
4
9
16
```

__Note:-__ They can only be used once.

## Yield

Yield is used as *return* but using yeild, function becomes a generator and returns a generator object on function calling.

When *yield* is encountered in a function it returns value and pauses the execution then again resumes execution on next iteration.

```
def generator():
    i = 0

    for i in range(5):
        yield i*2

gen = generator()

print(gen)

for i in gen:
    print(i)

for i in gen:
    print(i)
```
__Output__
```
<generator object generator at 0x102e7c660>
0
2
4
6
8
```


## References

* https://www.w3schools.com/PYTHON/
* https://www.geeksforgeeks.org/decorators-in-python/
* https://www.geeksforgeeks.org/generators-in-python/
* https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do
* https://www.w3schools.com/python/python_iterators.asp
* https://www.geeksforgeeks.org/iterators-in-python/
