[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)

# `Python` Data Types

In this part,  you will get better understanding with `Python`'s basic data type. We will look at **string** and **number** data type in this section. Also covered are:

- Data conversion
- Data comparison
- Receive input from users and display results effectively 

You will be guided through  completing a simple program which receives input from a user, process the information, and display results with specific format. 

## String

A `string` is a *sequence of characters*. We are using strings in almost every `Python` programs. As we can seen in the **”Hello, World!”** example, strings can be specified using single quotes **'**. The **print()** function can be used to display a string.

```Python
print('Hello, World!')
```

We can also use a variable to store the string value, and use the variable in the **print()** function.

```Python
# Assign a string to a variable 
text = 'Hello, World!'
print(text)
```

A *variable* is basically a name that represents (or refers to) some value. We use **=** to assign a value to a variable before we use it. Variable names are given by a programmer
in a way that the program is easy to understanding. Variable names are *case sensitive*. It can consist of letters, digits and underscores. However, it can not begin with a digit. For example, **plan9** and **plan_9** are valid names, where **9plan** is not.

```Python
text = 'Hello, World!'
# with print() function, content is displayed without quotation mark
print(text)
```

With variables, we can also display its value without **print()** function. Note that you can not display a variable without **print()** function in `Python` script(i.e. in a **.py** file). This method only works under interactive mode (i.e. in the notebook).  

```Python
# without print() function, quotation mark is displayed together with content
text 
```

Back to representation of string, there will be issues if you need to include a quotation mark in the text. We provide a example use a apostrophe mark(’) similar with single quotation mark('). You will find that it will show `SyntaxError: invalid character in identifier`. Just try to change the apostrophe mark with single quotation mark and run it again.

Since strings in double quotes **"** work exactly the same way as string in single quotes. By mixing these two types, it is easy to include quotation mark itself in the text.

```Python
text = "What' s your name?"
print(text)
```

You can specify multi-line strings using triple quotes  (**"""** or **'''**). In this way, single quotes and double quotes can be used freely in the text. Here is one example:

```Python
multiline = '''This is a test for multiline. This is the first line. 
This is the second line. 
I asked, "What's your name?"'''
print(multiline)
```

Another way of include the special characters, such as single quotes is with help of escape sequences `\`. For example, you can specify the single quote using *`\'`* as follows.

```Python
string = 'What\'s your name?'
print(string)
```

### Number

There are two types of numbers that are used most frequently: `integer` and `float`. As we expect, the standard mathematical operation can be applied to these two types. Please try the following expressions. Note that **`**`** is exponent operator, which indicates exponentiation exponential (power) calculation.

```Python
2 + 3
```

*Operator precedence* is a rule that affects how an expression is evaluated. As we learned in high school, the multiplication is done first than the addition. e.g. **2 + 3 * 4**. This means multiplication operator has higher precedence than the addition operator.

For your reference, a complete precedence table can be found under the heading "`Python Operators Precedence`" in this [Python tutorial](http://www.tutorialspoint.com/python/python_basic_operators.htm). However, When things get confused, it is far better to use parentheses **()** to explicitly
specify the precedence. This makes the program more readable.

Similarly as `string`, variables can be used to store a number so that it is easy to manipulate them. Here are some examples on operator precedence:

```Python
x = 3
y = 2
x + 2
sum = x + y
sum
```

### Data conversion and comparison

So far, we have seen three types of data: `integer`, `float`, and `string`. With various data type, `Python` can define the operations possible on them and the storage method for each of them. In the later [session](M01G-AdvDataTypes.md), we will further introduce more data types, such as `tuple`, `list` and `dictionary`. 

To obtain the data type of a variable or a value, we can use built-in function **type()**; whereas functions, such as **str()**, **int()**, **float()**, are used to convert data one type to another. Check the following examples on the usage of these functions:

```Python
type('Hello, world!)')
```

```Python
input_Value = '45.6'
type(input_Value)
```

```Python
weight = float(input_Value) % this will convert the user input into variable `weight` with the float data type, such as `45.6` as a number.
weight
type(weight)
```

Comparison between two values can help make decision in a program. The result of the comparison is either **True** or **False**. They are the two values of *`Boolean`* type.

```Python
# Double equal sign is also used for comparison
10.0 == 10
```

There are three logical operators, *`not`*, *`and`* and *`or`*, which can be applied to the `Boolean` values. 

```Python
# Both conditional #1 and conditional #2 are False?
not ((3 > 4) or (7 > 8))
```

### Input and Output

All programming languages provide features to interact with user. `Python` provide *input()* function to get input. It waits for the user to type some input and press return. We can add some information for the user by putting a message inside the function's brackets. It must be a string or a string variable. The text that was typed can be saved in a variable. Here is one example:

```Python
nInput  = input('Enter you number here:\n')
```

However, be aware that the input received from the user are treated as a `string`, even though a user entered a number. The following **print()** function invokes an error message. 

```Python
print(nInput + 3)
```

The input need to be converted to an integer before the match operation can be performed as follows because the string data cannot add the integer data directly. They are totally different two types of data.

```Python
print(int(nInput) + 3)
```

After user's input are accepted, the messages need to be displayed to the user accordingly. String concatenation is one way to display messages which incorporate variable values.
You can also use `print()` function with string formatting. We need to use the string formatting operator, the percent (%) sign.


```Python
name = 'David'
print('Hello, %s' % name)
age = 23
print('%s is %d years old.' % (name, age))
```

Notice that the two variables, **name**, **age**, that specify the values are included at the end of the statement, and enclosed with a bracket. 

With the quotation mark,  **`%s`** and **`%d`** are used to specify formatting for `string` and `integer` respectively. The following table shows a selected set of symbols which can be used along with `%`. 


```Python
# With %f, the format is right justification by default. 
# As a result, white spaces are added to the left of the number
# 10.4 means minimal width 10 with 4 decimal points
print('Output a float number: %10.4f' % (3.5))
```

## Activity

![GitHub watchers](https://img.shields.io/badge/MDS-Learning--Activity-yellow)
> 1. Load and run the notebook [M01C-DataTypes.ipynb](https://github.com/tulip-lab/sit742/blob/main/Jupyter/M01-Python/M01C-DataTypes.ipynb) from [![GitHub watchers](https://img.shields.io/badge/tulip--lab-sit742-brightgreen?style=plastic)](https://github.com/tulip-lab/sit742), and 
> 2. try different variants of the source code and see their effects.

