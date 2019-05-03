# Web Scraping with Python Tutorial (2nd Edition)

## Sources
This repository contains `ipynb` tutorials for the book [Web Scraping with Python: Collecting More Data from the Modern Web 2nd Edition](https://www.amazon.com/Web-Scraping-Python-Collecting-Modern/dp/1491985577/). All code snippets are modified from textbook examples. The copy right belongs to authors of the book.

## Environments
I use Python 3.7 in this repository. I also strongly recommend you to use Anaconda to manage Python environment, creating a virtual environment and installing packages like `BeautifulSoup` and `pandas`. Note that within the environment `pip` also works.

## Intentions
Some readers may wonder why I create this tutorial with codes in the textbook. First and foremost, I would like to learn web scraping techinques myself, so I create this repository to record my learning path.

Besides, I hope this repository could be a roadmap for readers to quickly look up frequent functions without search in the book or through the Internet. For example, I usually print only first 5-10 outputs for better display effect. I try to use expressions as concise as possible to help you save your time while still find what you need. For example, the book doesn't explain the concept of `decode()` very well, but I add both `ascii` and `utf-8` to make it clear.

Furthermore, although the 2nd edition is relatively new, some techniques in the book are not effective. For example, the book uses Python standard `csv` library to deal with CSV files where we can use one-liner in `pandas` to eaisly solve the problem. Here's the comparison:

**Method using `csv`:**
```py
from io import StringIO
import csv

data = urlopen('http://pythonscraping.com/files/MontyPythonAlbums.csv').read().decode('ascii', 'ignore')
dataFile = StringIO(data)
csvReader = csv.reader(dataFile)

for row in csvReader:
    print(row)
    print("The album \""+row[0]+"\" was released in "+str(row[1]))
```

**Method using `pandas`:**
```py
import pandas as pd

df = pd.read_csv("http://pythonscraping.com/files/MontyPythonAlbums.csv")
df
```

## Contents

This repository is still updating. I recommend you to read the notebooks through following links (using nbview instead of github).

|Chapter|Notebook|Notes|
|---|---|---|
|1. Your First Web Scraper|[chapter01.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter01.ipynb)|`urllib.request`, `urllib.error`, `from bs4 import BeautifulSoup`|
|2. Advanced HTML Parsing|[chapter02.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter02.ipynb)|`bs.find`, `bs.find_all`, `re`|
|3. Writing Web Crawlers|[chapter03.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter03.ipynb)|`re`, Crawling Across the Internet|
|4. Web Crawling Models|[chapter04.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter04.ipynb)|Structuring Crawlers|
|5. Scrapy||See details in textbook|
|6. Storing Data|[chapter06.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter06.ipynb)|Photos, CSV|
|7. Reading Documents|[chapter07.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter07.ipynb)|Text, CSV|
|8. Cleaning Your Dirty Data|[chapter08.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter08.ipynb)|n-grams|
|9. Reading and Writing Natural Languages|[chapter09.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter09.ipynb)|n-grams, Markov Models|
|10. Crawling Through Forms and Logins|[chapter10.ipynb](https://nbviewer.jupyter.org/github/SiweiShen2019/web-scraping-with-python-tutorial/blob/master/chapter10.ipynb)|Forms, Authentication|
