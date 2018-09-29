---
layout: post
title: Learn Python in 10 minutes for Data scientists
subtitle: This blog will  help you  start working on data using Python as quickly as possible. It is also useful for a quick refresh
gh-repo: vasubandaru/vasubandaru.github.io
gh-badge: [star, fork, follow]
tags: [Python]
---

This article list downs the things that you would need most frequently while working exploring and manipulating datasets. It will be easy, if you've already taken a basic course on Python. Don't worry you can start for now without any experience.

## Let's start

### Step 0: Install Anaconda

> [Anaconda](https://www.anaconda.com/download/)

We'll be using Python 3 in this article.
After installing, fire up your Spyder(IDE) or Jupyter(notebook) to start coding

### Libraries
Apart from basic operations, you would need libraries for most of the functions like reading data, summarizing etc. . The most frequently used libraries in data science are
> Numpy  
> Pandas  
> Scipy  
> Scikit-Learn  
> Matplotlib  

To download libraries either use command prompt OR anaconda prompt . You can also download them from  Jupyter/IPython notebook

```python
#From command prompt
pip install pandas

#If you don't have root access on your Linux/Unix terminal
sudo pip install pandas

#From Jupyter
!pip install pandas
```
You need to import these libraries before you use them

```python
import pandas as pd
import numpy as np
```
### Read data and explore
To read a csv file we will be using, read_csv from pandas. This we give us a dataframe.

```python
df = pd.read_csv('http://winterolympicsmedals.com/medals.csv')
```

Let's look at the data we've just read. It's shape,columns, head etc.

```python
df.shape #(Rows,Columns)
```

```
(2311, 8)
```

Returns a tuple of number of rows and columns. (Ha.. Tuple another data type)



```python
df.columns
```

```
Index(['Year', 'City', 'Sport', 'Discipline', 'NOC', 'Event', 'Event gender',
       'Medal'],
      dtype='object')
```

Returns array with column names



```python
df.head()
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
      <th>Discipline</th>
      <th>NOC</th>
      <th>Event</th>
      <th>Event gender</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>M</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>W</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>pairs</td>
      <td>X</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh</td>
      <td>BEL</td>
      <td>four-man</td>
      <td>M</td>
      <td>Bronze</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Ice Hockey</td>
      <td>Ice Hockey</td>
      <td>CAN</td>
      <td>ice hockey</td>
      <td>M</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>

</div>



```python
#Specify number of rows
df.head(2)
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
      <th>Discipline</th>
      <th>NOC</th>
      <th>Event</th>
      <th>Event gender</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>M</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>W</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>

</div>



Tip : Use tail() to get last rows, head(-n) to get (#rows - n) observations 

```python
#Get the description of all numeric columns
df.describe()
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2311.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1980.361748</td>
    </tr>
    <tr>
      <th>std</th>
      <td>22.089091</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1924.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1968.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1988.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1998.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2006.000000</td>
    </tr>
  </tbody>
</table>
</div>


#### Subsetting & Indexing

Chasing for the required columns and rows we want, is the daily routine. Let's see how it is done  
As I see it there are 3 main ways we subset i.e. Index, Name and Logical.In python we will be using two functions for this

> loc - works using labels
> iloc -  works using position - only integers



Let's start with some thing simple, choosing a row. We will use iloc now

```python
#In python indexing starts with 0, unlike in R
df.iloc[0,:]
```



```
Year                      1924
City                  Chamonix
Sport                  Skating
Discipline      Figure skating
NOC                        AUT
Event               individual
Event gender                 M
Medal                   Silver
Name: 0, dtype: object
```



This returns a single row as a Series(?)
When you want multiple rows, you specify the required position as a list(?) or range. How?

```python
df.iloc[[0,1,2],:] # [0,1,2] is a list
```



<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
      <th>Discipline</th>
      <th>NOC</th>
      <th>Event</th>
      <th>Event gender</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>M</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>W</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>pairs</td>
      <td>X</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>

</div>



```python
df.iloc[0:3,:] # Note not 0:2 we're using 0:3
```



<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
      <th>Discipline</th>
      <th>NOC</th>
      <th>Event</th>
      <th>Event gender</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>M</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>W</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>pairs</td>
      <td>X</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>

</div>



Note: Another way to do whatever we've done before is

> df.iloc[0]
> df.iloc[[0,1,2]]
> df.iloc[0:3]

Now Let's subset the columns

```python
df.iloc[:,0] # To select the first column and all rows
```

```python
df.iloc[:,0:3] # To select the first 3 columns and all rows
```

```python
df.iloc[0:3,0:3] # To select the first 3 columns and first 3 rows
```



<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
    </tr>
  </tbody>
</table>

</div>



But we won't be using column numbers most of the times, we use names. So how do we do it

```python
df['Year'] #Single Column
```

```python
df[['Year','Sport']] #Multiple Columns
```

When we want a combination numbe subsetting for rows and names for column, One way is

```python
df.iloc[0:3][['Year','Sport']] # OR df[['Year','Sport']].iloc[0:3] (potayto, potahto...)
```



<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Sport</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Skating</td>
    </tr>
  </tbody>
</table>

</div>



Ohh we're done with most of the subsetting,we haven't used **loc** function. May be we just don't need it. Hmmm, Let's see Can we use **loc** to do what we've done just

```python
df.loc[0:3,['Year','Sport']] # Just note that when we used 0:3 we got more than when using iloc
```



<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Sport</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Skating</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1924</td>
      <td>Bobsleigh</td>
    </tr>
  </tbody>
</table>

</div>



Yeah we can, but there is just one catch. As i said at the start loc works with _labels_. They are the column names and row names (or Indexes). Let's see what that means

```python
df.columns
```



```
Index(['Year', 'City', 'Sport', 'Discipline', 'NOC', 'Event', 'Event gender',
       'Medal'],
      dtype='object')
```



```python
df.index
```



```
RangeIndex(start=0, stop=2311, step=1)

```



There is mostly no problem with column labels, the problem is with row labels. ALthough in most of the cases the row labels are just a range of numbers from 0 to #rows, in some cases they are not.

To check this we'will take a subset of data and change their row labels or Indexes.

```python
df1 = df.iloc[0:5]
df1.shape
```



```
(5, 8)

```



```python
df1.index
```



```
RangeIndex(start=0, stop=5, step=1)

```



```python
df1.loc[0:3,]
```



<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}

```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
      <th>Discipline</th>
      <th>NOC</th>
      <th>Event</th>
      <th>Event gender</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>M</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>W</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>pairs</td>
      <td>X</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh</td>
      <td>BEL</td>
      <td>four-man</td>
      <td>M</td>
      <td>Bronze</td>
    </tr>
  </tbody>
</table>

</div>



Let's change the index and run the same command.

```python
df1.index = [0,33,11,44,3]
df1.index
```



```
Int64Index([0, 33, 11, 44, 3], dtype='int64')

```

```python
df1.loc[0:3,]
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}

```

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>City</th>
      <th>Sport</th>
      <th>Discipline</th>
      <th>NOC</th>
      <th>Event</th>
      <th>Event gender</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>M</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>33</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>individual</td>
      <td>W</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Skating</td>
      <td>Figure skating</td>
      <td>AUT</td>
      <td>pairs</td>
      <td>X</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>44</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh</td>
      <td>BEL</td>
      <td>four-man</td>
      <td>M</td>
      <td>Bronze</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1924</td>
      <td>Chamonix</td>
      <td>Ice Hockey</td>
      <td>Ice Hockey</td>
      <td>CAN</td>
      <td>ice hockey</td>
      <td>M</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>

</div>



As we can see in the output, it is giving the result till the label.
