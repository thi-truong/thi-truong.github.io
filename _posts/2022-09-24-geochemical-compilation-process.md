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

I have a penchant for the program IgPet to make geochemical figures because of the ease of generating bivariate plots with minimal steps. On the superficial side, I like the default appearance of the plots. I really dislike Excel "shadows" and and not quite 1 pt lines! I think that IgPet also brings me closer to the goal of learning tidy data.

I have a primary Windows laptop that I use for dissertating (LaTeX, Zotero), data processing (Excel, sometimes play around with Python and SQL), and general use. I also am borrowing a MacBook Pro from my department, solely to use the program IgPet, for which my research group has a Mac OS X site license, but not one for Windows. I am still considering paying the $300 fee for a Windows site license, because you'll come to see the my brain can only tolerate a small level of things-being-in-several-places before I start to forget they exist, or that I was searching for those things to begin with.

Today, I am making a simple "mantle components"/endmember/reservoir (I should know this) diagram based on [Stracke et al. (2012)](https://www.sciencedirect.com/science/article/pii/S000925411200366X), where there are plots showing such components, but no straightforward single value or uncertainty for them. So I must go fishing in the supplementary data to create my own. I acknowledge there are probably much more streamlined ways to do this, however, this process is likely to be a frequent one for me, even if I accomplish more efficient means in the future.


# Working across computers

## Microsoft Excel

* Download the supplementary file, which has the amazing file name "1-s2.0-S000925411200366X-mmc1.xls". It goes into "My Downloads" folder on Windows.
* Move the file to Hawaiian Literature--> Supplementary Data Files-->rename to Stracke2012-supp-table-1. Get lost trying to find "open in new window" option in the huge Windows right click toolbar.
* Table 1 shows 2 tabs: "Data" and "References". I will duplicate "Data" and then rename former to "Data (original)", "References (original)".
* I work in "Data" tab, knowing that the original data is also within reach, if needed.
* Assign unique number values into left side. There is probably a better way to do this, but I have them as 1 to 4939. I also freeze paned first column and row for ease of looking at the data. 

![image](https://user-images.githubusercontent.com/92915699/192112331-6b066799-d89c-4462-82ef-df72f467a575.png)

* I inspect what I am working with. I want to produce a sheet where every row/column is a value, so I look for remove columns that are not needed. I end up deleting C and D because they are not numerical and I can go back to that data any time because of the unique numbers I made. Renamed Series name to the new labels that I want. I am keeping the series number because it is actually useful (I can use it as a JCode or something).

![image](https://user-images.githubusercontent.com/92915699/192112241-4b9f13e0-2007-405e-ba4f-5a9fbe7fe2c4.png)

There are almost 5,000 values in this sheet, so I wanted to see if I could streamline grouping everything without turning it all into a table. [Learned how to jump to unique values](https://superuser.com/questions/873242/is-there-a-way-to-skip-down-to-the-next-change-in-value-in-excel) (start of 1, end of 1 or start of 2, end of 2 or start of 3... by highlighting column C and pressing CTRL + SHIFT + \. The only problem is that has to be done from the beginning every time. how can you highlight a column but in the middle? You can't! Okay it's faster to just copy the first 3 rows and add 1 to the leftmost row later.

![image](https://user-images.githubusercontent.com/92915699/192112774-2bb7872b-45ae-4efc-9967-e6014b90abd5.png)

For series 1-5, I wrote them all out. For 7, I thought, oh I could just copy and paste and still use the keyboard shortcut. but that spit me out to the beginning. So I just went through the whole thing again with the keyboard shortcut. By the time I got to 13, I decided to just manually scroll through the rows, spot new series numbers, and simply copy and paste the rows, and add 1 later to each number in the leftmost column.

![image](https://user-images.githubusercontent.com/92915699/192112869-a447ff2d-f497-46c8-980b-703b19d32ebf.png)

Though I could easily pull down the formula to easily calculate the rest up to row 26, I had to delete the first row without compromising the latter. So I copied the new calculations and pasted into a new column, then replaced the calculation column so that I could safely delete the stuff in column A without causing errors.

Next step was to fill in column D "Row End" with the next row start minus 1. Added 4940 for the last, or else it was -1.
![image](https://user-images.githubusercontent.com/92915699/192112978-a4a285fe-169f-446c-91c8-ec2d0624b33d.png)

Did a random check with series 7 Samoa and series 22 Iceland to make sure the row start and ends are correct, and indeed they are.

By this time, the process has taken 30 minutes. I paste over the info as plain text in a new tab "Information". I had been doing this all in another sheet solely so that I could have windows side by side. This is way easier than navigating tab-to-tab within one sheet (I get lost easily and forget what I was doing).

I experiment with making an Sr-Nd plot that has all the series with correct names. I make the first one for Series 1 and 2 by manually dragging the "Select data" tool to the spreadsheet. For the rest, I want to semi-automate it by changing the data cell numbers (rows). I may manually select the locality names but we'll see. The pai of plots-in-progress in Excel are that I never know where to find them within the sheet when I am done selecting the data. This plot sits in the rows where presumably, the last series group starts. At least I think that's the logic. Still tough in a nearly 5,000 row sheet. I do not make the plot in anew tab because of aforementioned object permanence issues, but maybe soon I can do that.


I manually create the plot with the first two groups (as in, I go to "Select Data" and I select data by clicking and dragging cells on the sheet, opposed to typing them into the fields. Atlantic and Pacific MORB are shown here. I am reminded by how easy it is to lose this plot when scrolling.

![image](https://user-images.githubusercontent.com/92915699/192113128-03d4e123-35bb-4688-8c0c-4be93abd8ee9.png)

Now that I know the "formulas" and have things set up, I tried to challenge myself to see if I could plot the rest of the 23 groups in the Sr-Nd plot in 5 minutes. My most efficient system involves working on two screens, where the [left screen is the large external monitor where the Excel action happens](https://user-images.githubusercontent.com/92915699/192113203-f8106b2a-11a7-4a9a-92ee-dabeeb2c3420.png) and the [right screen is my laptop, where the information is kept in sequential order](https://user-images.githubusercontent.com/92915699/192113194-212f9f7b-91c3-42f6-9cbb-748d87a3eed6.png)

That did not work. You can't really streamline manually adding a group to plot in the "select data" function. It's all one-by-one.

Yes, I am aware there is a data editor somewhere that allows me to make a plot through some kind of Excel code, but I am taking the simple way out today to make a point. Because of weird Excel copy/paste issues, I should write theses formulas in plain text and paste them one by one in the edit series maker. 

20 minutes later, I have made progresse because I actually pre-wrote all the formulas on a separate notepad file to paste, one by one, into the Excel fields.

Why is this happening? All the Canary Island values are fine and not acidentally off by orders of magnitude...

![image](https://user-images.githubusercontent.com/92915699/192114551-13fc567e-4e99-4e03-9a4c-8d97bab4f705.png)

This is what happens when you plot Canary Islands alone...

![image](https://user-images.githubusercontent.com/92915699/192114580-2caae585-bb05-456a-a39c-5e2df56442d9.png)

I have no patience for this, so I deleted the Canary Islands. Sorry. This is the Sr-Nd plot:

![image](https://user-images.githubusercontent.com/92915699/192114624-cce8a25e-48f9-43e6-822e-580f80329b8e.png)

Now I am wondering if I even set myself up at all to plot Pb-Pb-Pb plots with this system. I think I still have to go group by group (all 25) and painstakingly replace the column letters!

## IgPet 
Starting at about 12:20, I copied and pasted all the data into a new sheet, and I made sure to have first column renamed to "Sample", and then include the JCode, KCode, and LCode columns.

![image](https://user-images.githubusercontent.com/92915699/192115066-12a28b2f-f954-4339-abcb-64a9ca26be75.png)

 I do not have symbols or legend codes figured out yet, but this should plot okay. Conveniently, the excel file where I tracked the series number will be useful because I can actually make the legend very quickly in a notepad file. I set both KCode and JCode as tbe same thing (seems to be my standard practice unless something changes...I think I wanted to work in some consistency).
 
 ![image](https://user-images.githubusercontent.com/92915699/192115215-9d83f735-8b66-467a-b726-c04f0293b6c4.png)

I go over to the MacBook which I always put to sleep, so turning it on takes about 10 seconds. I have a Dropbox document folder synced up, though it's not the SAME IgPetDocs folder as on the Macbook, becuase I am still not sure how these things work. It's still an instantly transferrable file, even if I have some not-super-matching redundant folders. This took a minute:

<img width="1680" alt="Screen Shot 2022-09-24 at 12 29 16 PM" src="https://user-images.githubusercontent.com/92915699/192115378-416873a3-9a58-4a1b-9ade-b7e019f4fcb7.png">

This was done quickly to demonstrate how quickly I could make a plot, but it is not ready to show with my data yet. For  that, i just have to make sure all the column headers match. I'll standardize this next. I made this in a few minutes:

<img width="627" alt="Screen Shot 2022-09-24 at 12 38 44 PM" src="https://user-images.githubusercontent.com/92915699/192115674-82f682f0-c09b-42cd-ba69-ab376e283075.png">

# Conclusion

Total time to make a Sr-Nd plot in Excel with literature compilation: Roughly 1.5 hours. Part of that was due to me familiarizing myself with Excel on Windows 11 and not knowing *all* the tips and tricks that one should probably know by now.

Total time to make an IgPet plot of Sr-Nd, Pb-Pb-Pb: Roughly 15 minutes, where most of that was spent data wrangling the 25 groups of samples. The actual plotting took maybe 5 minutes, and I did not alter any of the symbols, font size, design, etc.
