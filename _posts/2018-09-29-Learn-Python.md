---
layout: post
title: Learn or Refresh Python in 10 minutes for Data scientists
subtitle: I wanted to help you get started working with Python on real data as quickly as possible. That is what this page is about.
gh-repo: vasubandaru/vasubandaru.github.io
gh-badge: [star, fork, follow]
tags: [Pyton] [DataScience] [DataScientist]
---

# Learn or Refresh Python in 10 minutes for Data scientists

![](C:\Users\Vasumani.Bandaru\Pictures\blog1.png)

### I wanted to help you get started working with Python on real data as quickly as possible. That is what this page is about.

This article list downs the things that you would need most frequently while working with data. It will be easy, if you've already taken a basic course on Python.

### Let's start

**Step 0:** Download 

[Python]: https://www.python.org/downloads/

 and 

[Anaconda]: https://www.anaconda.com/download/

We'll be using Python 3 format in this blog

```python
!pip install twitter
```


```python
import pandas as pd
from twitter import *
```


```python
tweets = pd.read_csv('C:/Users/Vasumani.Bandaru/Downloads/delete-tweets-master/tweets.csv')
```


```python
tweets.head()
```

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tweet_id</th>
      <th>in_reply_to_status_id</th>
      <th>in_reply_to_user_id</th>
      <th>timestamp</th>
      <th>source</th>
      <th>text</th>
      <th>retweeted_status_id</th>
      <th>retweeted_status_user_id</th>
      <th>retweeted_status_timestamp</th>
      <th>expanded_urls</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>853950333319495680</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2017-04-17 12:36:39 +0000</td>
      <td>&lt;a href="http://twitter.com/download/android" ...</td>
      <td>What abt your own delays (AI-460 Vijayawada to...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>https://www.google.co.in/amp/wap.business-stan...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>853947835766657024</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2017-04-17 12:26:44 +0000</td>
      <td>&lt;a href="http://twitter.com/download/android" ...</td>
      <td>AIR-460 dlyd by 8 hrs. Vijayawada airport nd m...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>853117178941382657</td>
      <td>8.525822e+17</td>
      <td>44196397.0</td>
      <td>2017-04-15 05:26:00 +0000</td>
      <td>&lt;a href="http://twitter.com/download/android" ...</td>
      <td>@elonmusk any timeframe for India release?</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>851405461903429634</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2017-04-10 12:04:15 +0000</td>
      <td>&lt;a href="http://twitter.com/download/android" ...</td>
      <td>RT @carterjwm: HELP ME PLEASE. A MAN NEEDS HIS...</td>
      <td>8.498136e+17</td>
      <td>2.568271e+09</td>
      <td>2017-04-06 02:38:40 +0000</td>
      <td>https://twitter.com/carterjwm/status/849813577...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>842596860070043648</td>
      <td>NaN</td>
      <td>244413282.0</td>
      <td>2017-03-17 04:42:00 +0000</td>
      <td>&lt;a href="http://twitter.com/download/android" ...</td>
      <td>@SpectranetCare Internet frqntly goes down, fa...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>


```python

```
