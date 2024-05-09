[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)


# Advanced Data Types

## List

**List is a sequence**. Like a string, a **list** is a sequence of values. The values in a list can be any type. We call the values **items** of the list. To create a list, enclose the items in square brackets.

For example, 

```Python
shoplist = ['apple', 'mango', 'carrot', 'banana']
l = [10, 20, 30, 40]
empty = [ ]   # Initialize an empty list
```

The elements of a list do not have to be the same type. Another list can also be nested inside a list. 

To access the element of a list, use the bracket operator to obtain the value available at the index. Note that the indices of list start at 0. You can also use negative value as index, if you count from right. For example, the negative index of last item is -1. Try the following examples:


```Python
l = [10, 20, 30, 40]
l[2]
l[-1]
l[-3]
```

Here is an example of nested list: 

```Python
l = ['apple', 2.0, 5, [10, 20]]
l[1]  
l[3]
l[3][1]  
```

Unlike strings, lists are mutable, which means they can be altered. We use bracket on the left side of an assignment to assign a value to a list item.

```Python
l = [10, 20, 30, 40]
l[1] = 200
l
```

### **Traverse a list**

The most common way to traverse the items of a list is with a **for** loop. Try the following code:

```Python
shoplist = ['apple', 'mango', 'carrot', 'banana']
for item in shoplist:
    print(item)
```

This works well if you only need to read the items of the list. However, you will need to use indices if you want to update the elements. In this case, you need to combine the function **range()** and **len()**.  


```Python
l = [2, 3, 5, 7]

for i in range(len(l)):
       l[i] = l[i] * 2

print(l)
```

How it works:

**len()** returns the number of items in the list, while **range(n)** returns a list from 0 to n - 1. By combining function **len()** and **range()**, **i** gets the index of the next element in each pass through the loop. The assignment statement then uses **i** to perform the operation.


## Tuple

### Tuple are immutable 

A **tuple** is also a sequence of values, and can be any type. Tuples and lists are very similar. The important difference is that tuples are immutable, which means they can not be changed. 

Tuples is typically used to group and organising data into a single compound value.  For example, 


```Python
year_born =  ('David Hilton', 1995)
year_born
```

To define a tuple, we use a list of values separated by comma. 
Although it is not necessary, it is common to enclose tuples in parentheses. 

Most list operators also work on tuples. 
The bracket operator indexes an item of tuples, and the slice operator works in similar way. 

Here is how to define a tuple:


```Python
t  = ( ) # Empty tuple
t
```

### Tuple assignment

Tuple assignment allows a tuple of variables on the left of an assignment to be assigned values from a tuple on the right of the assignment. 
(We already saw this type of statements in the previous prac)

For example,
 

```Python
t = ('David', '0233', 78)
(name, id, score) = t
name 
id
score
```

### Lists and tuples

It is common to have a list of tuples. For loop can be used to traverse the data.  For example,


```Python
t = [('David', 90), ('John', 88), ('James', 70)]

for (name, score) in t:
       print(name, score) 
```

## Dictionary

A **dictionary** is like an address-book where you can find the address or contact details of a person by knowing only his/her name. The way of achieving this is to associate **keys**(names) with **values**(details). Note that the key in a dictionary must be unique. Otherwise, we are not able to locate correct information through the key. 

Also, worth noted is that we can only use immutable objects(strings, tuples) for the keys, but we can use either immutable or mutable objects for the values of the dictionary. This means that we can use either a string, a tuple or a list for dictionary values.

The following example defines a dictionary: 

```Python
dict = {'David': 70, 'John': 60, 'Mike': 85}
dict['David']
dict['Anne'] = 92  # add an new item in the dictionary
dict
```

### **Traverse a dictionary**

The key-value pairs in a dictionary are **not** ordered in any manner. The following example uses **for** loop to traversal a dictionary. Notice that the keys are in no particular order. 

```Python
dict = {'David': 70, 'John': 60, 'Amy': 85}

for key in dict:
    print(key, dict[key])
```

However, we can sort the keys of dictionary before using it if necessary. The following example sorts the keys and stored the result in a list **sortedKey**. The **for** loop then iterates through list **sortedKey**. The items in the dictionary can then be accessed via the names in alphabetical order. Note that dictionary's **keys()** method is used to return a list of all the available keys in the dictionary. 

```Python
dict = {'David': 70, 'John': 60, 'Amy': 85}
sortedKeys = sorted(dict.keys())

for key in sortedKeys:
    print(key, dict[key])

```

## Activity

![GitHub watchers](https://img.shields.io/badge/MDS-Learning--Activity-yellow)
> 1. Load and run the notebook [M01G-AdvDataTypes.ipynb](https://github.com/tulip-lab/sit742/blob/main/Jupyter/M01-Python/M01G-AdvDataTypes.ipynb) from [![GitHub watchers](https://img.shields.io/badge/tulip--lab-sit742-brightgreen?style=plastic)](https://github.com/tulip-lab/sit742), and 
> 2. try different variants of the source code and see their effects.


