[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)

# Control Flow

Normally, 
*`Python`* executes a series of statement in exact top-down order. What if you want to change the flow how it works? 
As you might have guessed, in this prac, we will first look at **control flow**  statements. We are going to practice on three control flow statements, i.e.,  **if**, **for** and **while**, to see how they can determine what statement is to be executed next in a program.  

Second, we will look at how to create, read, and write files in *Python*. We have obtained data via interaction with users in previous prac. Now let us explore how to deal with files to get input of a program and write output that can be used later. 

##  **`If`** statements

The **`if`** statement is used to check a condition: **if** the condition is true, we run a block of statements(**if-block**), **else** we process another block of statement(**else-block**). The **else** clause is optional. The condition is usually a boolean expression, which can have value of **True** or **False**. 

Often we have a block of statement inside either **if-block** or **else-block**. In this case, you need to especially pay attention to the indentation of the statements in the block. Indenting starts a block and unindenting ends it. As a general practice, `Python` style guide recommend using 4 white spaces for indenting a block, and not using tabs. If you get indentation error message from `Python` interpreter, you will need to check your code carefully. 
 
```Python
x = 15
if x % 2 == 0:
    print('%d is even' % x)
else:
    print('%d is odd' % x)
    
print('This is always printed') 
```

Try change **x** to even number (such as 16) and run the program again.

The else-block in **if** statement is optional. If the **else** block is omitted,  the statements in **if**-block are executed when the condition equal to **True**. Otherwise, the flow of execution continues to the statement after the **if** structure. 

Try the following code:    

```Python
x = -2
if x < 0:
    print("The negative number %d  is not valid here." % x)
    
print("This is always printed")
```

What will be printed if the value of `x` is negative?

If statement can also be nested within another. Further if structure can either be nested in `if`-block or `else`-block. Here is an example with another `if` structure nested in `else`-block.

This example assume we have two integer variables, `x` and `y`. The code shows how we might decide how they are related to each other.

```Python
x = 10
y = 10

if x < y:
    print("x is less than y")
else:
    if x > y:
        print("x is greater than y")
    else:
        print("x and y must be equal")
```

Here we can see that the indentation pattern can tell the `Python` interpreter exactly which else belong to which `if`.

`Python` also provides an alternative way to write nested if statement. We need to use keyword `elif`. The above example is equivalent to :

```Python
x = 10
y = 10

if (x < y):
    print("x is less than y")
elif (x > y):
    print("x is greater than y")
else:
    print("x and y must be equal")
```

`elif` is an abbreviation of `else if`. With above structure, each condition is checked in order. If one of them is `True`, the corresponding branch executes. Even if more than one condition is `True`, only the first `True` branch executes.

There is no limit of the number of `elif` statements, but only a single final `else` statement is allowed. The `else` statement must be the last branch in the statement.

##  **`For`** statements

Computers are often used to automate repetitive tasks. Repeated execution of a sequence of statements is called **iteration**. Two language features provided by Python are **while** and **for** statement. We first take a look an example of **for** statement:


```Python
for name in ["Joe", "Amy", "Brad", "Angelina", "Zuki"]:
    print("Hi %s Please come to my party on Saturday!" % name)

```

This example assume we have some friends, and we would like to send them an invitation to our party. With all the name in the list, we can print a message for each friend. 

This is how the **for** statement works:

1. **name** in the **for** statement is called loop variables, and the names in the square brackets is called **list** in Python. We will cover more details on list in next prac. For now, you just need to know how to use simple list in a **for** loop. 

2.  The second line in the program is the **loop body**. All the statements in the loop body is indented.

3.  On each iteration of the loop, the loop variable is updated to refer to the next item in the list. In the above case, the loop body is executed 5 times, and each time name will refer to a different fiend. 

4. At the end of each execution of the body of the loop, Python returns to the **for** statement to handle the next items. This continues until there are no item left. Then program execution continues at the next statement after the loop body.      


One function commonly used in loop statement is **range()**.
	
Let us first have a look at the following example:
	
```Python
for i in [0, 1, 2, 3, 4 ]:
    print( 'The count is %d' % i)
```

Actually generating lists with a specific number of integers is a very common task, especially in **for** loop. For this purpose,  `Python` provides a built-in **range()** function to generate a sequence of values. An alternative way of performing above counting using **range()** is as follows.

```Python
for i in range(5):
    print( 'The count is %d' % i)
print('Good bye!')
```

>Notice **range(5)** generates a list of $5$ values starting with 0 instead 1. In addition, 5 is not included in the list. 
	
### **`While`** statements

The **`while`** statement provides a much more general mechanism for iteration. It allows you to repeatedly execute a block of statements as long as a condition is **True**. 

Similar to the **if** statement, the **while** statement uses a Boolean expression to control the flow of execution. The body of **while** will be repeated as long as the condition of boolean expression equal to **True**.

Let us see how the previous counting program can be implemented by **while** statement.

```Python
i = 0
while (i < 6):
    print('The count is %d' % i)
    i = i + 1
    
print('Good bye!')
```

How the `while` statement works:
1. The **`while`** block consists of the print and increment statements. They are executed repeatedly until count is no longer less than $6$. With each iteration, the current value of the index count is displayed and then increased by $1$. 

2. Same as **`for`** loop, this type of flow is also called a loop since **`while`** statements is executed repeatedly. Notice that if the condition is **False** at the first time through the loop, the statement inside the loop are never executed. Try change the first line into **i = 6**. What is the output?

2. In this example, we can prove that the loop terminates because **i** start from $0$ and increase by $1$. Eventually, **i** will be greater than 5. When the condition becomes **False**, the loop stops. 
	
3. Sometime, we will have loop that repeats forever. This is called an infinite loop. Although this kind of loop might be useful sometimes, it is often caused by a programming mistake. Try to change the first two lines of previous program into the following code. See what happen? 

Note that if you run the following cell, the code will run indefinitely. You will need to go to the menu: **Kernel->Restart**, and then restart the kernel.

Also note that if you run such code in `Python` at command line or script mode, you will need to use <kbd>CTRL</kbd>+<kbd>C</kbd> to terminate the program.

```Python
i =  6
while i > 5 :  
    print('The count is %d' % i)
    i = i + 1
    
print('Good bye!')
```

## **`Break`** statements

The **`break`** statement can be used to break out of a loop statement. It can be used both in **`while`** loop and **`for`** loop. 

Alternative way of previous counting example with **`break`** statement is as follows:

```Python
i =  0
while True :
    print( 'The count is %d' % i)
    i = i + 1
    if i > 6:
        break
        
print('Good bye!')
``` 

In this program, we repeated print value of **i** and increase it by 1 each time. We provide a special condition to stop the program by checking if **i** is greater than 6. We then break out of the loop and continue executed the statement after the loop.  

Note that it is important to decide what the terminated condition should be. We can see from previous counting example that the terminated condition might be different in different `loop` structure.  


## Activity

> 1. Load and run the notebook [M01D-ControlFlow.ipynb](https://github.com/tulip-lab/sit742/blob/main/Jupyter/M01-Python/M01D-ControlFlow.ipynb) from [![GitHub watchers](https://img.shields.io/badge/tulip--lab-sit742-brightgreen?style=plastic)](https://github.com/tulip-lab/sit742), and 
> 2. try different variants of the source code and see their effects.

