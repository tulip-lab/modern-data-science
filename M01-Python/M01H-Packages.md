[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)


# Python Packages

## Python Standard Library 

After completing previous Python sessions, you should know about the syntax and semantics of the Python language. But apart from that, you should also learn about Python libraries and its packages to be able to code efficiently. Python’s standard library is very extensive, offering a wide range of facilities as indicated [here](https://docs.python.org/3/library/index.html). The library contains built-in modules (written in `C`) that provide access to system functionality such as file I/O that would otherwise be inaccessible to Python programmers, as well as modules written in Python that provide standardised solutions for many problems that occur in everyday programming. Look at the [Python Standard Library Manual](https://docs.python.org/3/library/index.html) to read more.

For a complete list of Python standard library and their documentation look at the [Python Manual.](https://docs.python.org/3/library/) A few to mention are:

* ``math`` for numeric and math-related functions and data types
* ``urllib`` for fetching data across the web
* ``datetime`` for manipulating dates and times
* ``pickle`` and ``cPickle`` for serialising and deserializing data structures enabling us to save our variables on the disk and load them from the disk
* ``os`` for operating system dependent functions

### Importing a module

To use a module, first you have to ``import`` it. There are different ways to import a module:

* `import my_module`
* `from my_module import my_function`
* `from my_module import my_function as func`
* `from my_module import submodule`
* `from my_module import submodule as sub`
* `from my_module import *`

**`'import my_module'`** imports the module `'my_module'` and creates a reference to it in the namespace. For example `'import math'` imports the module `'math'` into the namespace. After importing the module this way, you can use the dot operator `(.)` to refer to the objects defined in the module. For example `'math.exp()'` refers to function `'exp()'` in module `'math'`.

```Python
import math

x = 2
y1 = math.exp(x)
y2 = math.log(x)

print("e^{} is {} and log({}) is {}".format(x, y1, x, y2))
```

**`'from my_module import my_function'`** only imports the function `'my_function'` from the module `'my_module'` into the namespace. This way you won't have access to neither the module (since you have not imported the module), nor the other objects of the module. You can only have access to the object you have imported.

You can use a comma to import multiple objects.

```Python
from math import exp

x = 2
y = exp(x)  # no need to math.exp()

print("e^{} is {}".format(x, y))
```

**`'from my_module import my_function as func'`** imports the function `'my_function'` from module `'my_module'`, but its identifier in the namespace is changed into `'func'`. This syntax is used to import submodules of a module as well. For example later you will see that nowadays it is almost a convention to import `matplotlib.pyplot` as `plt`.

```Python
# you can change the name of the imported object
from math import exp as myfun

x = 2
y = myfun(x)

print("e^{} is {}".format(x, y))
```

**`'from my_module import *'`** imports all the public objects defined in `'my_module'` into the namespace. Therefore, after this statement you can simply use the plain name of the object to refer to it and there is no need to use the dot operator:

```Python
from math import *

x = 2
y1 = exp(x)
y2 = log(x)

print("e^{} is {} and log({}) is {}".format(x, y1, x, y2))
```


## Third-Party Python Packages

In addition to the standard library, there is a growing collection of several thousand components (from individual programs and modules to packages and entire application development frameworks), available from the [Python Package Index](https://pypi.org/). There are thousands of third party packages, each developed for a special task. Some useful libraries for data science are:

* ``numpy`` is probably the most fundamental package for efficient scientific computing in Python
* ``scipy`` is one of the core packages for scientific computations
* ``pandas`` is a library for operating with table-like data structures called `DataFrame` object
* ``matplotlib`` is a comprehensive plotting library
* ``BeautifulSoup`` is an HTML and XML parser
* ``scikit-learn`` is the most general machine learning library for Python
* ``nltk`` is a toolkit for natural language processing

We will learn their usage when we meet them in later data science modules.

```Python
import math

x = 2
y1 = math.exp(x)
y2 = math.log(x)

print("e^{} is {} and log({}) is {}".format(x, y1, x, y2))
```

<details><summary>:movie_camera:</summary>

![Video](https://img.shields.io/badge/tulip--lab-SIT742--ScreenVideo-brightgreen) 
- Packages
- Link as below: 
https://deakin.zoom.us/rec/share/AyrtRY8qPFp3toec7iCjcF_aIZyahkFz3MQWW0xnSkZoc4gI1FwKcjYQtSp6Nv7E.nuYZaqf2AbCJIVun?startTime=1635340648000
</details>

>[![Packages](https://img.youtube.com/vi/oLtJG622-VA/0.jpg)](https://www.youtube.com/watch?v=oLtJG622-VA   "Packages")


## :biking_man: Activity

![GitHub watchers](https://img.shields.io/badge/MDS-Learning--Activity-yellow)
> 1. Load and run the notebook [M01H-Packages.ipynb](https://github.com/tulip-lab/sit742/blob/main/Jupyter/M02-Python/M02H-Packages.ipynb) from [![GitHub watchers](https://img.shields.io/badge/tulip--lab-sit742-brightgreen?style=plastic)](https://github.com/tulip-lab/sit742), and try different variants of the source code.
> 2. Write code to implement the following tasks: a) Import the library math from standard Python libraries; b) Define a variable and assign an integer value to it (smaller than 20); c) Use factorial() function (an object in math library) to calculate the factorial of the variable; d) and print its value.
> 3. Write code to implement the following tasks: a) Write a function that takes an integer variable and returns its factorial; b) Use this function to find the factorial of the variable defined in above; c) Check whether your answers match?




