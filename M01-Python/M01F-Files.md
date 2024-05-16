[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)

# **Files**

we will look at how to create, read, and write files in *·*. 
We have obtained data via interaction with users in previous prac. Now let us explore how to deal with files to get input of a program and write output that can be used later. 


## Using files

### Reading files

You can open and use files for reading or writing by creating an object of the *file class*.  The *mode* that is specified for the file opening decides what you can do with the file: read, write or both. Then the file object's **read()** or **write()** method can be used to read from or write to the file. Finally, when you are finished with the file, you call the **close()** method to tell Python that you are done using the file. 

Here is an example. You can download the data file **[score.txt](https://github.com/tulip-lab/sit742/raw/master/Jupyter/data/score.txt)**, which includes data on students' score. The format of the data file is as follows:


```
Name, Student ID, Score

David 3402 80
Jane 3403 76
Sophia 3405 65
Jane 3447 92
William 3456 75 
```

For Online platforms such as Google Colab, it is important for you to get familiar with the provided data storage or cloud data storage function. Alternatively, you might want to directly access the file, and load into your Notebook.


```Python
!pip install wget
```

Then you can download the file into GPFS file system.


```Python
import wget

link_to_data = 'https://github.com/tulip-lab/sit742/raw/master/Jupyter/data/score.txt'
DataSet = wget.download(link_to_data)

print(DataSet)
```

The following example reads from the **.txt** file and display information on the screen. Please type the code and run it under script mode. Make sure **score.txt** are saved under your **data** folder.


```Python
scorefile = open('score.txt','r')

for line in scorefile:
    value = line.split()
    name = value[0]
    id = value[1]
    score = value[2]
    print('%s with ID %s has a score of %s' % (name, id, score))

```

How the program works:
1. The **open()** function is used to open a file. You need to specify the name of the file and the mode in which you want to open the file. The mode can be read mode('`r`'), write mode('`w`') or append mode('`a`'). There are actually many more modes available. You can get more details by create a cell and typing ""`open?`"". Please try this in your notebook. When we finish working on the file, we  need to close the file using **close()** method. 

	
2. To process all of the data, we use a **for** loop to iterate over the lines of the file. The **line** variable is a string that is used to store characters in each line.
	 
     
3. We use the **split()** method to break each line into a list containing all the fields of interest. We can then take the value corresponding to **name**, **id** and **score** and print them in the sentence. To get each data item in a list, we use index with the list. e.g. values[0] will return the item of position 0 in the list.  Note that in Python the position of items in a list is starting from 0. 

## Writing to files

One of the most commonly performed data processing tasks is to read data from a file, manipulate it in some way and then write the resulting data out to a new data file to be used for other purpose later. For creating a new file used for writing, the same **open()** function is used. Instead of using '`r`' mode, '`w`' mode is used as the parameter. When we open a file for writing, a new, empty file with the specified name is created and ready to accept our data. 

As an example, consider the **score.txt** data again. Assume we have request to remove the name information in the file for privacy issue. Therefore, the output file need  to have student ID with the scores separated by a comma.  Here is how we can generate the required file. 

```Python
infile = open('score.txt', 'r')
outfile = open('id.txt', 'w')

for line in infile:
    values = line.split()
    id = values[1]
    score = values[2]
    dataline = id + ',' + score

    outfile.write(dataline + '\n')

infile.close()
outfile.close()
```

You can use the `print()` to print file content on the console.

```Python
f=open('id.txt', 'r')
message=f.read()
print(message)
f.close
```


How the program works:

1. We have add another **open()** method with 'w' mode. The filename **id.txt** is chosen to store the data. If the file does not exist, it will be created. However, if the file does exist, it will be reinitialised and empty, and any previous contents will be lost 
2. We have variable **dataline** to store what need to be write in the file. If you like, you can add a line **print(dataline)** to check the string value. We then call function **write()** method to write **dataline** into the file.
3. There is one additional part we need to add when writing to file. The newline character **\n** need to be concatenated to the end of the line. Otherwise, the text will be all in one continuous line.  
4. The file needs to be closed at the end.  


## CSV file 

In this part, we will see how to read and write data from **`CSV`** file. *CSV (Comma Separated Values)* format is the most common import and export format for **speadsheets** and databases. With knowledge from above part, we should be able to open **CSV** file as normal text file, loop over the lines, and use **split** method to get individual columns. 
However, we will in this prac learn to use a *`Python`* built-in module, *CSV*, to simplify the whole process. 


### Import CSV module

As mentioned earlier, Python provides a **csv** module which makes it easier to deal with **csv** file. A *module* is a program file that contains a collection of related functions. Before we can use the module, we have to add the following line at the beginning of our program to import the module. 

```Python
import csv
```

### Read  CSV file 

To read data from a **csv** file, use the **reader()** function to create a reader object. The **reader** function will take each line of the file and make a list containing all that line's columns. The following example reads the file and prints items on each row.  

Please download **[score.csv](https://github.com/tulip-lab/sit742/raw/master/Jupyter/data/score.csv)** file before running the following program.
 
```Python
import csv          #import module before reading from CSV file

link_to_csv = 'https://raw.githubusercontent.com/tulip-lab/sit742/master/Jupyter/data/score.csv'
csvdata = wget.download(link_to_csv)

infile = open('/content/score.csv','r')
incsv = csv.reader(infile, delimiter = ',')

rowNum = 0
for row in incsv:
    if rowNum != 0:   
        # if this is not the first row      
        id, name, score = row
        print("%s %s %s" % (id, name, score))
    rowNum += 1

infile.close()  
```

How it works:

1.  The **open()** function opens the **csv** file using flag "r". 
	
2.  We use **csv.reader** to refer to the **reader()** function in the **csv** module. Inside the parentheses of the function, we also indicated that the **csv** file uses *comma* as a *delimiter*.  
		
3. Within the **for** loop, each row that is read from the file are stored into variable **row**, which represents a list of strings. The items of the list are then  assigned to individual variables for further processing. 

4. The **if** statement in the **for** loop is used to skip the header row. Since we do not need the information in the header row, this row is simply skipped. 

5. Notice that the following lines are needed to initialise **rowNum** and increment its value. 

>
>```python
>...
>	rowNum = 0
>	for row in incsv
>		...
>		rowNum += 1
>...		
>```

### Write CSV file

To write `CSV` files,  use **writer()** to create an object for writing, then iterate over the rows using **writerow()** to print them. Note in the following example, **id** and **score** are first stored in **rowOutput**, which represents a list of string. Then the list `rowOutput` is passed to **writerow()** method so that values of **id** and **score** can be written to the file. 

```Python
import csv

infile = open("data/score.csv", "r")
incsv = csv.reader(infile, delimiter = ',')
outfile = open("data/id.csv", "w")
outcsv = csv.writer(outfile, delimiter=',')

rowNum = 0
for row in incsv:
    if rowNum != 0:         # skip first row
        id, name, score = row
        rowOutput = [id, score]
        outcsv.writerow(rowOutput) 
    rowNum += 1

infile.close()
outfile.close()
```

<details><summary>:movie_camera:</summary>

![Video](https://img.shields.io/badge/tulip--lab-SIT742--ScreenVideo-brightgreen) 
- Files
- Link as below: 
https://deakin.zoom.us/rec/share/x6Kl9QDf-29xd3Y_ZCvFXtcOKA5PTpuvK3gCZkRH7KphMPaOPucIlSrUTShRBuY7.ZNglwEFSicWgULHO?startTime=1635345023000
</details> 

>[![Files](https://img.youtube.com/vi/T-MNr0viTh4/0.jpg)](https://www.youtube.com/watch?v=T-MNr0viTh4    "Files")

## :biking_man: Activity

![GitHub watchers](https://img.shields.io/badge/MDS-Learning--Activity-yellow)
> 1. Load and run the notebook [M01F-Files.ipynb](https://github.com/tulip-lab/sit742/blob/main/Jupyter/M02-Python/M02F-Files.ipynb) from [![GitHub watchers](https://img.shields.io/badge/tulip--lab-sit742-brightgreen?style=plastic)](https://github.com/tulip-lab/sit742), and 
> 2. try different variants of the source code and see their effects.


