[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)

# **PoP** vs **OoP**

`Functions` are reusable pieces of `programs`. They allow you to give a name to a block of statements, allowing you to run that block using the specified name anywhere in your program and any number of times. We have already used some built-in functions such as **range()**, **type()**. 

In the first part of this session, we will look closely at  how to define and use your own function, and how to use the functions in `Python` modules. These modules come with `Python` as part of its standard library. When designing programs around functions, we call this **Procedure-oriented Programming** (PoP). 

Another way of organising your program is to combine data and functionality and wrap it inside something called an **`object`**. This is called the **Object-oriented Programming** (OoP) paradigm. In the second part of this session, you will see how to use `Object-oriented` (OO) features provided by `Python` to develop programs.

## Function

### Definition and use 

While we can use the functions that come with `Python`, it is also possible to add new functions. A *function definition* includes two parts:

1.  a *header*, which begins with a keyword **`def`**, followed by a pair of parentheses which may enclose some names of variables, and by the final colon that ends the line. 

2. a *body* consisting of one or more Python statements. All the statements in the block has same indentation - $4$ spaces is the `Python` standard - from the header.

Here we define a simple function. The function definition looks like this:  

```Python
def say_hello():
	print('Hello world!')
```

Note the keyword **`def`** is followed by function name **say\_hello**. The empty parentheses indicate that it has no parameters. Its body only contains one single statement, which print a text **Hello world**.

After defining a function, we need to *call* a function to make it run. Since the **say\_hello** function have an empty parameter list, the function calls do not take any arguments. Notice, however, that the parentheses are still required in the *function call*:

```Python
def say_hello():
    print('Hello world!')

say_hello()
```

### Parameters and arguments ###

Most functions require arguments, values that control how the function does its job. For example, `Python` has a built-in function for computing the absolute value:

```Python
abs(5)
abs(-5)
```

In this example, the argument of **abs** function are **5** and **-5**. You can use expression as arguments as well. 

Inside the function, the variables that are assigned to the values are called *`parameters`*. Here is an example of a user-defined function that has one parameter:

```Python
def print_twice(param):
    print(param + ' ' + param)
```

This function takes a single argument and assigns it to the parameter named `param`. To test the function, we call this function as follows:

```Python
print_twice('SIT742')
```

### Variables and parameters are local ###

When you create a local variable inside a function, it only exists inside the function, and you can not use it outside. In this case, we say the **scope** of the variable is within the function. For example, if we run the following code, we will get an error:

```Python
def cat_twice(part1, part2):
    cat = part1 + part2
    print(cat)
    print(cat)

str1 = 'Good'
str2 = 'Morning'
cat_twice(str1, str2)
print(cat)
```

What happens:
- The function **cat\_twice** takes two arguments, concatenates 
them, and then prints the result twice.

- After defining the function, we call the function with **str1**
and **str2**, and then try to print variable **cat**. However,
when **cat\_twice** terminates, variable **cat** is destroyed. If we try to print it, we get an error. 

- Parameters are also local.  If we try to use **part1** and 
**part2** outside of function **cat\_twice**, `Python` will 
complain as well.

### Return values ###

A lot of built-in function, such as **abs()**, **max()**, have 
produced results. Calling each of these functions generates a value, which can be assigned to a variable or used in an expression.

```Python
bigger = max(3,5)
bigger
```

We can also write our own functions that return values. Here is an example **area**, which returns the area of a circle with the given **radius**:

```Python
def area(radius):
    temp = 3.14159 * radius ** 2
    return temp

print(area(3))
```

The **return** statement means: the process will return immediately from this function, and use the following expression (such as `temp`) as the return value. For above example, we can also use an expression, 
such as `3.14159 * radius ** 2`, as the return value. 


```Python
def area(radius):
    return 3.14159 * radius ** 2

print(area(3))
```

Notice that the flow of execution can not reach a statement if it
appears after a *return* statement. This kind of code is called dead code.

A `Python` function returns a special value **None** whenever they do not return another value. Here is an example:

```Python
def absolute_value(x):
    if x < 0:
        return -x
    elif x > 0:
        return x

print(absolute_value(0))
```

Note that if `x` equals to $0$, neither condition is true, and the function ends without hitting a `return` statement. In this case, the return value is `None`. `None` is the unique value of a type called the `NoneType`.

### Docstrings 

*Docstring* is an important tool that you should make use of, 
since it helps to document the program better and makes it easier to understand. The following example adds **docstring** to the **cat\_twice** function. You can   save the script  as **cat\_twice.py**


```Python
def cat_twice(part1, part2):
    """ Concatenates part1 and part 2, and 
    prints the result twice.
    """
    cat = part1 + part2
    print(cat)
    print(cat) 
```

This `docstring` is a triple-quoted string. The `docstring` contain the essential information for using the function. It explains what the function does, and what effect each parameter has on the behaviour of the function. Note that `docsting` 
also applies to modules and classes.

If you have used **help()** in `Python`, then you have already seen the usage of `docstings`! What it does is just fetch the `docstring` of that function and display it for you. 

Try the following command:

```Python
help(cat_twice)     # function name used as an argument in  help() function
```

Writing this kind of documentation is an important part of program development. If you are having a hard time explaining one of your functions, that might be a sign that the design of your function could be improved.


## Module

A *module* is a file that contains a collection of related functions. The **math** module in `Python` provides most of the familiar mathematical functions.  

```Python
import math
math.pi      # Variable pi from the module
```

The **import** statement creates a module object named **math**. The module object contains the functions and variables defined in the module. To access one of the functions, you have to specify the name of the module and the name of the function, separated by a dot. For information on other functions defined in the math module, type `help(math)` under interactive mode. 

`Python` provides two ways to import modules, we have already seen one:

```Python
from math import pi
```

Now you can access **pi** directly.

```Python
print(pi)
```

The advantage of importing everything from the `math` module is that your code can be more concise. The disadvantage is that there might be conflicts between names defined in different modules, or between a name from a module and one of your variable. 


## Class and object 

In this part, we will start by introducing how to define and use a `class`.  We will then look at the difference between `class` and `object` variables, and finally discuss one of the most important concepts in OoP, **inheritance**. 


`Class` and `objects` are two main aspects of OoP. **Class** creates a new type, whereas **objects** are the *instances* of the class. Object can store data using ordinary variables that *belong* to the object. Variables that belong to an object or class are referred to as *`attributes`*. Objects can also have functionality that is bound to it by defining functions that belong to a class. Such functions are called **`methods`** of the `class`. It is important to differentiate between functions and variables which are independent and those which belong to a class or object. 

### Classes

A `class` is created using the **class** keyword. The attributes and methods of the class are listed in an indented block. 

The simplest `class` possible is shown in the following example. 

```Python
class Person:
    pass    # An empty block

p = Person()
print(p)
```

How it works:

1.  We create a new class using the **`class`** statement. Then an indented block of statements is used to form the body of the class. Note the **`pass`** statement indicates an empty block in this case. 
2.  We then create an object of this class using the name of 
the class followed by a pair of parentheses. We check the type of the variable by simply printing it. The message tells us that we have an instance of the **Person** class. 
3.  Note that the address of the computer memory where the object is stored is also printed. The address will have a different value on your computer. 


### Methods

Classes/objects can have **methods** just like functions. 
The difference is that the definition of method is indented and included in the class definition. In addition, all the class methods have an extra **self** variable. 

```Python
class Person:
    def say_hi(self):
        print('Hi, how are you doing?')

p = Person()
p.say_hi()
```

As mentioned, class method have one specific difference from ordinary functions. They must have a parameter **self** as first item in the parameter list. When you call the method, however, you do not give a value for this parameter. Instead, `Python` will provide it. 

If you have a class **MyClass** and its object called **myobject**. When you call a method  **myobject.method(arg1, arg2)**, it is automatically converted by *Python* into **MyClass.method(myobject, arg1, arg2)**. This is all the special **self** is about. 


There are many methods that have special significance in `Python` classes. The **init** method is run as soon as an object of a class is instantiated. You can add any initialisation for the class object to this method. Notice the double underscores both at the beginning and at the end of the name. 

The following example demonstrates **init** method of the **Person** class. 


```Python
class Person:
    def __init__(self, name):
        self.name = name
    def say_hi(self):
        print('Hi, ' + self.name + ', how are you doing?')

p = Person("James Bond")
p.say_hi()
```

How it works:

1. We define the **`init`** method and pass a parameter name along with the usual self. In the method, a new attribute **`name`** is created. Notice that the dotted notion **`self.name`** means this variable is part of an object, while the other **name** is a local variable. By using dotted notation, there is no confusion between the two variables. 


2. We do not need to explicitly call the `init` method. Instead, the arguments is passed following the class name when creating a new instance of the class. This is the special significance of this method. 

### Class and Object variables

We have discussed the class method, i.e. functionality part of classes and objects. Now let us look at the data part. 
The data part, i.e. attributes, are just ordinary variables that are only valid within the context of these classes and objects only.

There are two types of attributes - **class variables** and **object variables** which are classified by whether the class or the object owns the variables respectively. 

Class variables are shared, and can be accessed by *all instances of that class*. When any object makes a change to a class variable, the change will be seen by all the other instances. 

Object variables are owned by *each individual instance* of the class. Each object has its own copy of the attribute. The following example demonstrates the difference between class variable and object variable. 

```Python
class Robot:
    """Example of DocString: Represents a robot, with a name."""
    # A class variable, counting the number of robots
    population = 0

    def __init__(self, name):
        """Initializes the data."""
        self.name = name
        print("(Initializing %s)" % (self.name))
        # When this person is created, the robot
        # adds to the population
        Robot.population += 1

    def die(self):
        """I am dying."""
        print("%s is being destroyed!" % self.name)
        Robot.population -= 1
        if Robot.population == 0:
            print("%s was the last one." % self.name)
        else:
            print("There are still %d robot(s) working." % Robot.population)

    def say_hi(self):
        """Greeting by the robot.
        Yeah, they can do that."""
        print("Greetings, my masters call me %s" % self.name)

    @classmethod
    def how_many(cls):
        """Prints the current population."""
        print("We have %d robot(s)." % cls.population)

droid1 = Robot("R2-D2")
droid1.say_hi()
Robot.how_many()
droid2 = Robot("C-3PO")
droid2.say_hi()
Robot.how_many()

print("\nRobots can do some work here.\n")
print("Robots have finished their work. So let's destroy them.")
droid1.die()
droid2.die()
Robot.how_many()
%print(Robot.__doc__)
```

How it works:

1.  **population** belongs to the **Robot** class and hence is a class variable. Therefore, we refer to the **population** variable as **Robot.population**. 

2.  The **name** variable belongs to the **Robot** class and hence is a class variable. As a result, we refer to variable **name** as **self.name** in the methods of the object. 

3.  The **how_many** is a method that belongs to the class instead of to the object. We define it as *classmethod*. We use a decorator **@classmethod** to mark the **how_many** method as a class method. In the **die** method, we simply decrease the **Robot.population** count by 1.

4.  The value of **self.name** is specific to each object which indicates the nature object variables. 

5.  We also see the use of *docstring* for classes as well as methods. We can access the class **docstring** at runtime using **Robot.\_\_doc\_\_** and the method *docstring* as **Robot.say_hi. \_\_doc\_\_**. You can uncomment the last statement to test run.

### Inheritance

*Inheritance* helps reuse of code, and is one of the most important features of object-oriented programming. Inheritance can be best imagined as implementing a type and subtype relationship between classes. 

Suppose you need to write a program to keep track of the information of the teachers and students. They have some common characteristics such as name and age, while also have specific characteristics such as salary for teachers, and marks for students. 

Instead of creating two independent classes for each type, a better way is to create a common class call **SchoolMember**, 
and then have the **Teacher** and **Student** classes inherit from this class. There are many advantages to this approach. 
If we add/change any functionality in **SchoolMember**, 
this is automatically reflected in the subtypes. 
However, changes in the subtypes do not affect other subtypes. 

Another advantage is that we can refer to a **Teacher** 
or **Student** object as a **SchoolMember** object. 
This is called *polymorphism* where a sub-type can be substituted in any situation where a parent type is expected, i.e. the object can be treated as an instance of the parent class. 

With inheritance, we can reuse the code of the parent class and do not need to repeat it in the different class. The **SchoolMember** class in this situation is called the *`base class`* or *`super class`*. The **Teacher** and **Student** classes are called the *`subclasses`*. 

This example shows how to define and use superclass and subclass.  

```Python
class SchoolMember:
    '''Represents any school member.'''
    def __init__(self, name, age):
        self.name = name
        self.age = age
        print('(Initialized SchoolMember: %s)' % self.name)

    def tell(self):
        '''Tell my details.'''
        print('Name: %s Age: %d' % (self.name, self.age))
        
class Teacher(SchoolMember):
    '''Represents a teacher.'''
    def __init__(self, name, age, salary):
        SchoolMember.__init__(self, name, age)
        self.salary = salary
        print('(Initialized Teacher: %s)' % self.name)

    def tell(self):
        SchoolMember.tell(self)
        print('Salary:  %d ' % self.salary)

class Student(SchoolMember):
    '''Represents a student.'''
    def __init__(self, name, age, marks):
        SchoolMember.__init__(self, name, age)
        self.marks = marks
        print('(Initialized Student: %s)' % self.name)

    def tell(self):
        SchoolMember.tell(self)
        print('Marks: %d' % self.marks)
        
t = Teacher('Dr. Zhu', 35, 50000)
s = Student('John Smith', 22, 75)
# prints a blank line
print('\n')
members = [t, s]
for member in members:
    # Works for both Teachers and Students
    member.tell()
```

How it works:

1. To use inheritance, we specify the base class name in the `tuple` (more on [`tuple`](M01G-AdvDataTypes.md#tuple)) following the class name in the definition, e.g. **def Teacher(SchoolMember)**. We also need to explicitly call the  **init** method of based class  in the **init** method of subclass. Note that *Python* does not automatically call the constructor of the base class. 

2. When we use the **tell** method of the **SchoolMember** class, 
we can treat instances of **Teacher** or **Student** as instances of the **SchoolMember**. 

3. When the **tell** method of **Teacher** class is called. 
`Python` actually starts to look for methods in the actual type, i.e. **Teacher** class. If it could not find the method, it then looks at the methods belonging to its base class, 
i.e. **SchoolMember** class.


## :biking_man: Activity
![GitHub watchers](https://img.shields.io/badge/MDS-Learning--Activity-yellow)

> 1. Load and run the notebook [M01E-PoP-OOP.ipynb](https://github.com/tulip-lab/sit742/blob/main/Jupyter/M02-Python/M02E-PoP-OOP.ipynb) from [![GitHub watchers](https://img.shields.io/badge/tulip--lab-sit742-brightgreen?style=plastic)](https://github.com/tulip-lab/sit742), and 
> 2. try different variants of the source code and see their effects.


