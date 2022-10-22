---
layout: post
title:  "Tennis Project"
date:   2022-10-21
author: Nano Carter
description: This is my project about the top 250 ATP players
image: /assets/images/download.jpg
---

# Top 250 ATP Players
### For this project I found data for the top 250 ATP tennis players which was moderately difficult but even more difficult was figuring out what data I wanted.
### Introduction
I have played tennis for a long time and I am interested in the ATP which is why I chose to obtain this data. At first I wanted to obtain more interesting data but it seemed to be challenging to obtain. For example I could have obtained information about the best servers in tennis from a table and added new columns to it. I think I was worried I wouldn't be able to easily get this data which is why I gave up on this data. It also was simply hard to choose what data to obtain when so many choices were available but no choice was the obvious choice. I chose data about the top 250 ATP players because I knew there would be information such as country where a player is from in a different data source.

### Obtaining Final Data Set
To obtain the final data set I got information from two sources. I scraped the ATP Tour website and a website called tennisexplorer. Most of the data came from the ATP Tour website while one column came from the tennisexplorer website. I faced some challenges getting this data set. One of the challenges was that many websites didn't have enough players in their rankings. Another challenge was that some had a load more button which I don't know how to deal with. One different challenge was that some websites didn't have the country of players from Russia becuase they aren't allowed to represent Russia currently.

### Details of Obtaining Data Set
I used BeautifulSoup to obtain my dataset. I don't have much experience with APIs which is why I decided to use BeautifulSoup and used code that should be familiar.
```
import pandas as pd
import numpy as np
from bs4 import BeautifulSoup
import requests
import re
r = requests.get(url)
r.status_code
soup = BeautifulSoup(r.content, 'html.parser')
```
I used list comprehensions to get my data as well as soup.find_all where I found specific classes such as the code below.
```
rank = soup.find_all(class_='rank-cell border-left-4 border-right-dash-1')
rank1 = [i.string for i in rank]
```
After getting the data from the ATP Tour website I got data from tennisexplorer which was on multiple urls and my code probably is very inefficent but I stil got the data I wanted. There were many more things I did to clean the data into the data I wanted but to keep this post short I won't go into details. My data ended up looking like this.

![Figure](https://raw.githubusercontent.com/152151/stat386-projects/main/assets/images/Table.png)


### Ethics
I believe it was legal to scrape based on the discussion we had in class which told me that it was most likely legal because of a Supreme Court ruling. One website kicked me off their website for web scraping and I didn't obtain data from that website which is a potential way to know if it's ethical/legal. I went to the robots.txt for the ATP Tour website and it is kind of debatable whether they want people to be webscraping what I webscraped but I think because it is public and easily found data it is ethical and legal. The robots.txt on the tennisxplorer website seems to allow webscraping the data which I did.

### Conclusion
I am going to try and extract as much interesting information as I can from this dataset. I will try and find unexpected results so that my exploratory data analyis has good insights. This might only be interesting to those that play or watch tennis but I will do my best with the data set I obtained.

### Link to GitHub repo

https://github.com/152151/Tennis_Project



