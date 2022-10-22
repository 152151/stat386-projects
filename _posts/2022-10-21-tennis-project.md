---
layout: post
title:  "Tennis Project"
date:   2022-10-21
author: Nano Carter
description: This is my project about tennis data
image: /assets/images/blog-image.jpg
---

# Top ATP 250 Players
### For this project I found data for the top ATP 250 tennis players which was moderately difficult but even more difficult was figuring out what data I wanted.
### Introduction
I have played tennis for a long time and I am interested in the ATP which is why I chose to obtain this data. At first I wanted to obtain more interesting data but it seemed to be challenging to obtain. For example I could have obtained information about the best servers in tennis from a table and added new columns to it. I think I was worried I wouldn't be able to easily get more information about the same players which is why I gave up on this kind of data. It also was simply hard to choose what data to obtain when there were so many choices but no choice being the obvious choice. I chose data about the top 250 ATP players because I knew there would be infromation such as country from a different data source.

### Obtaining Final Data Set
To obtain the final data set I got information from two sources. I scraped the ATP Tour website and a website called tennis explorer. Most of the data comes from the ATP Tour website while one column comes from the tennis explorer website. I faced some challenges getting this Data Set. One of the challenges was that many websites didn't have enough players in their rankings. Another challenge was that some had a load more button which I don't know how to deal with. One different challenge was that some websites didn't have the country of Russian players becuase they aren't allowed to represent Russia currently.

### Details of Obtaining Data Set
I used BeautifulSoup to obtain my dataset. I don't have much experience with APIs which is why I decided to use Beautiful Soup and used code that should be very familiar.
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
After getting the data from the ATP Tour website I got data from tennis explorer which was on multiple urls and my code probably is very inefficent but I stil got the data I wanted. There were many more things I did to clean the data into the dataframe I wanted but to keep this post short I won't go into details.

![Figure](https://raw.githubusercontent.com/152151/stat386-projects/main/assets/images/Screenshot%20(48).png)

### Ethics
I believe it was legal to web scrape based on the discussion we had in class which told me that it was most likely legal based off of a Supreme Court ruling. One website kicked me off their website for web scraping and I didn't obtain data from that website which is a way to know if it's ethical. I went to the robots.txt for the ATP Tour website and it is kind of debateable whether they want people to be webscraping what I webscraped but I think because it is public and easily found data it is ethical. The robots.txt on the tennisxplorer website seems to allow webscraping the data which I did.


### Conclusion
I am going to try and extract as much interesting information as I can from this dataset. I will try and find unexpected results so that my exploratory data analyis has good insights. This might only be interesting to those that play or watch tennis but I will do my best with the data I obtained.

### Link to GitHub repo


 
 


