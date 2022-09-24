---
title: 'Geochemical Data Compilation Process'
date: 2022-01-16
permalink: /posts/2022/09/24/geochemical-compilation-process
tags:
  - data
  - geochemistry
  - learning
---

Sometimes I wonder if my data compilation process is too haphazard, random, and unorganized. So I will swing the other way and be overly organized and document my steps. I am not confident that this will help anyone else, but it will be useful for me when I inevitably retrace my steps to produce figures from the data that I compile. 

# Working across computers

I have a penchant for the program IgPet to make geochemical figures because of the ease of generating bivariate plots with minimal steps. On the superficial side, I like the default appearance of the plots. I really dislike Excel "shadows" and and not quite 1 pt lines! I think that IgPet also brings me closer to the goal of learning tidy data.

I have a primary Windows laptop that I use for dissertating (LaTeX, Zotero), data processing (Excel, sometimes play around with Python and SQL), and general use. I also am borrowing a MacBook Pro from my department, solely to use the program IgPet, for which my research group has a Mac OS X site license, but not one for Windows. I am still considering paying the $300 fee for a Windows site license, because you'll come to see the my brain can only tolerate a small level of things-being-in-several-places before I start to forget they exist, or that I was searching for those things to begin with.

Today, I am making a simple "mantle components"/endmember/reservoir (I should know this) diagram based on [Stracke et al. (2012)](https://www.sciencedirect.com/science/article/pii/S000925411200366X), where there are plots showing such components, but no straightforward single value or uncertainty for them. So I must go fishing in the supplementary data to create my own. I acknowledge there are probably much more streamlined ways to do this, however, this process is likely to be a frequent one for me, even if I accomplish more efficient means in the future.

* Download the supplementary file, which has the amazing file name "1-s2.0-S000925411200366X-mmc1.xls". It goes into "My Downloads" folder on Windows.
* Move the file to Hawaiian Literature--> Supplementary Data Files-->rename to Stracke2012-supp-table-1. Get lost trying to find "open in new window" option in the huge Windows right click toolbar.
* Table 1 shows 2 tabs: "Data" and "References". I will duplicate "Data" and then rename former to "Data (original)", "References (original".
* I will inspect Data and start to remove columns that are not needed, and see if there is an easy way to preserve original order

![image](https://user-images.githubusercontent.com/92915699/192112241-4b9f13e0-2007-405e-ba4f-5a9fbe7fe2c4.png)

Assign unique number values into left side. There is probably a better way to do this, but I have them as 1 to 4939. I also freeze paned first column and row for ease of looking at the data.

![image](https://user-images.githubusercontent.com/92915699/192112331-6b066799-d89c-4462-82ef-df72f467a575.png)

Next is deleting rows that I do not need so that I can turn everything into a table. renaming Series name to the new labels that I want. I am keeping the series number because it is actually useful (I can use it as a JCode or something).

There are almost 5,000 values in this sheet, so I wanted to see if I could streamline grouping everything without turning it all into a table. [Learned how to jump to unique values](https://superuser.com/questions/873242/is-there-a-way-to-skip-down-to-the-next-change-in-value-in-excel) (start of 1, end of 1 or start of 2, end of 2 or start of 3... by highlighting column C and pressing CTRL + SHIFT + \. The only problem is that has to be done from the beginning every time. how can you highlight a column but in the middle? You can't! Okay it's faster to just copy the first 3 rows and add 1 to the leftmost row later.

![image](https://user-images.githubusercontent.com/92915699/192112774-2bb7872b-45ae-4efc-9967-e6014b90abd5.png)

For series 1-5, I wrote them all out. For 7, I thought, oh I could just copy and paste and still use the keyboard shortcut. but that spit me out to the beginning. So I just went through the whole thing again with the keyboard shortcut. By the time I got to 13, I decided to just manually scroll through the rows, spot new series numbers, and simply copy and paste the rows, and add 1 later to each number in the leftmost column.
