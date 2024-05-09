[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Modern--Data--Science-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Module-Python-orange)](README.md)

# Python Programming Platforms

## Why Programming?

**Data science** is empirical synthesis of actionable knowledge from raw data through the data lifecycle process. It extracts knowledge, models or insights from the raw data in various forms, either structured or unstructured. In this way, it is similar to **data mining**. With data which can be messy, has missing values, inconsistent formatting, malformed records and nonsensical outliers in practice, data science employs a wide range of techniques to collect, wrangle, manipulate and analyse the data.

While there might be multiple tools (such as [RapidMiner](https://rapidminer.com/), [Weka](http://www.cs.waikato.ac.nz/ml/weka/), [Excel](https://www.microsoft.com/en-au/microsoft-365/excel) or [Tableau](https://www.tableau.com/)) out there to assist in this job, the flexibility of *developing your own programs* is the most preferred in data science. There are more than a few reasons behind it.

- [Why would you use Python instead of RapidMiner?](https://community.rapidminer.com/discussion/56567/why-would-you-use-python-instead-of-rapidminer)
- [Why Data Scientists Must Speak the Language of Python](https://medium.com/@james_52456/why-data-scientists-must-speak-the-language-of-python-b280674e9985)
- [Why are Python & R so much more popular here than Weka/Java?](https://www.reddit.com/r/MachineLearning/comments/1rwj8p/why_are_python_r_so_much_more_popular_here_than/)

>:speaking_head: For the teaching purpose, we will use `Python` in this unit `SIT742: Big Data Analytics`.


## Python or R?

As you must know by now, it is a great choice to do data analysis using programming. Out there, there’s a battle taking place in minds of future data scientists for choosing the best programming languages. Though there are quite a number of tools with many options, the close combat narrows down between two popular languages – `Python` and `R`.

While I may be tempted to recommend `Python` straight-away as the chosen language in `MDS`, I want you to be aware of many interesting comparisons of the features of those two languages. For example, the following online articles:

- [R or Python for Data Science?](https://medium.com/codex/r-or-python-for-data-science-e2dc798a6c81)
- [Python vs R for Data Science: And the winner is...](https://medium.com/@datadrivenscience/python-vs-r-for-data-science-and-the-winner-is-3ebb1a968197)

The key differences between `Python` and `R` can be summarised as in the following Table:

| Features | `Python` | `R` |
| --- | :-- | :-- |
| Scope | Used for a variety of purposes like Web-applications development and data analysis | Used mainly for statistical modeling |
| Used by | data scientists, data engineers, software developer | Statisticians, Analyst and Data scientists |
| Suitable for | Beginners to experienced data scientists | People without prior programming knowledge |
| Package Distribution | [PyPi](https://pypi.org/) | [CRAN](https://cran.r-project.org/) |
| Visualisation Package | `Matplotlib`, `seaborn`, `bokkeh` | `ggplot2`, `plotly`, `ggiraph` | 

In short, `Python` is used for data analysis as well as Web application development, while `R` is most widely used for statistical modelling and data analysis. As what matters most as a beginner in Data Science is that you **DO Data Science**, you may just go with either one of the languages and prioritise getting some data science projects done while practising this unit. That’s how you will learn the fastest.

Along with Data Science, `Python` has also built a major force to conquer data manipulation, data analysis, artificial intelligence and machine learning. So if you learn `Python`, you are not limited to a career in data science or AI, many other career [opportunities](https://www.seek.com.au/python-jobs) have open doors for you. 


## Getting Started with `Python`

Depending on your technical background, you may resort to one of the following two platforms to start `Python` programming.

- **Cloud Platforms**: [Google Colab](https://colab.research.google.com), or [DataBricks](https://databricks.com/)(Community Version), etc.
- **Self-Hosting `Jupyter`**: [Anaconda](https://anaconda.org/), or [JupyterLab](https://jupyter.org/), etc.


You may consider different factors when choosing your preferred platform. The basic trade off is well-known: 

- If you use an **Cloud Platform**  like [Google Colab](https://colab.research.google.com), you don't need hardware, but the cost of running the instances will get expensive later, especially when analysing big data beyond the free-tier. 
- If you **self-host**, you need some dedicated hardware, most likely also need a graphics card if doing big data analysis or deep learning.

### `Google Colab`

>:speaking_head: For the teaching purpose, `Google Colab` is the selected teaching platform in `SIT742: Big Data Analytics`.

But as a beginner, this trade off doesn't come into play yet, since most practical sessions and case studies in `MDS` will train models within minutes. As a beginner, what you need is an easy to set up environment. In this case, [Google Colab](https://colab.research.google.com) wins hands down. 

- :page_with_curl: [Google Colab](M01A-Platforms-I.md)


### Self-Hosting `Jupyter`

>:bangbang: This part is optional if you will use `Google Colab` for this unit.

For data scientists with experience and IT skills, **self-hosting `Jupyter`** is the flexible option, and you need to install and configure the needed packages before using it.

- :page_with_curl: [`Jupyter`](M01A-Platforms-II.md)


![Readings](https://img.shields.io/badge/MDS-Extra--Readings-orange)
- [A study on using Python vs Weka on dialysis data analysis](https://doi.org/10.1109/INCIT.2017.8257883)
- [R vs Python](https://www.reddit.com/r/MachineLearning/comments/1rg8o4/r_vs_python/)
- [Python vs R for Data Science](https://towardsdatascience.com/python-vs-r-for-data-science-6a83e4541000)
- [Python vs. R for Data Science — What is the Difference?](https://medium.com/geekculture/python-vs-r-for-data-science-what-is-the-difference-4c7181659dc5)
