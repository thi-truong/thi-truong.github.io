---
title: 'Excel vs. IgPet. An informal geochemistry plotting showdown'
date: 2022-09-24
permalink: /posts/2022/09/24/geochemical-compilation-process
tags:
  - data
  - geochemistry
  - learning
---

I have a penchant for the program IgPet to make geochemical figures because of the ease of generating bivariate plots with minimal steps. On the superficial side, I like the default appearance of the plots. But IgPet brings me closer to the goal of learning tidy data.

Sometimes I wonder if my data compilation process is too haphazard, random, and unorganized when I use Microsoft Excel. I am aware that scientists are using it beyond the intended purpose to display accounting data. It makes sense that, while, "data processing", calculations, visualizations, etc., can be done on Excel, that does not mean that we *should*.

Still, perhaps the difficulties are mine alone, and I can work towards being more organized while documenting my workflow and issues. Today, I will be overly organized and document my steps. 

# Objective

Today, I am making a simple "mantle components" isotope diagram from [Stracke et al. (2012)](https://www.sciencedirect.com/science/article/pii/S000925411200366X). The paper contains figures showing such components, but no straightforward single value or data table for say, averages, etc. My simple goal is to create an <sup>87</sup>Sr/<sup>86</sup>Sr-<sup>143</sup>Nd/<sup>144</sup>Nd plot where the 25 groups are shown with different symbols

# The Showdown

I have a primary Windows laptop that I use for dissertating (LaTeX, Zotero), data processing (Excel, sometimes play around with Python and SQL), and general use. I will use this for the Microsoft Excel part, and the data processing for IgPet.

I also am borrowing a MacBook Pro from my department, solely to use the program IgPet, for which my research group has a Mac OS X site license, but not one for Windows. I do all of the data processing, organization, collating on the Windows, and simply generate figures on the Macbook. 

## Microsoft Excel

Disclaimer: I acknowledge there are probably much more streamlined ways to do this, however, this process is likely to be a frequent one for me, even if I accomplish more efficient means in the future.

### Data

* I go to the [Supplementary Table 1 on the science direct page](https://www.sciencedirect.com/science/article/pii/S000925411200366X#ec0005). I downloaded the spreadsheet which is an xls file. I save it with the default name, "1-s2.0-S000925411200366X-mmc1.xls". It goes into "My Downloads" folder on Windows, since it's easier for me to rename and move later rather than get this sorted upon download (maybe I dislike working in tiny dialog boxes...)
* I moved the file to Hawaiian Literature--> Supplementary Data Files-->rename to Stracke2012-supp-table-1. I almost got lost trying to find "open in new window" option in the huge Windows right click toolbar. There must be 3 dozen options in that toolbar.
* I open the file and see that Table 1 shows 2 tabs: "Data" and "References". I will duplicate "Data" and then rename former to "Data (original)", "References (original)".
* I work in "Data" tab, knowing that the original data is also within reach, if needed.
* * I inspect [the data sheet](https://user-images.githubusercontent.com/92915699/192112241-4b9f13e0-2007-405e-ba4f-5a9fbe7fe2c4.png) to see what I am working with.
* I want to produce a sheet where every row/column is a value, so I look for remove columns that are not needed. I end up deleting C and D because they are not numerical and will not be useful when plotting (not to worry, the data still lives in the other tab, "Data (original)".
* I assigned [unique number values into leftmost column](https://user-images.githubusercontent.com/92915699/192112331-6b066799-d89c-4462-82ef-df72f467a575.png). There is probably a better way to do this, but I have them as 1 to 4939. I also freeze paned first column and row for ease of looking at the data. 

### Plotting

I experiment with making an Sr-Nd plot that has all the series with correct names. I make the first one for Series 1 and 2 by manually dragging the "Select data" tool to the spreadsheet, opposed to typing them into the fields. Atlantic and Pacific MORB are shown here. I am reminded by how easy it is to lose this plot when scrolling.

![image](https://user-images.githubusercontent.com/92915699/192113128-03d4e123-35bb-4688-8c0c-4be93abd8ee9.png)

For the rest, I want to semi-automate it by changing the data cell numbers (rows). I may manually select the locality names but we'll see. The pair of plots-in-progress in Excel are that I never know where to find them within the sheet when I am done selecting the data. This plot sits in the rows where presumably, the last series group starts. At least I think that's the logic. Still tough in a nearly 5,000 row sheet. I do not make the plot in anew tab because of aforementioned object permanence issues, but maybe soon I can do that.

There are almost 5,000 values in this sheet, so I wanted to see if I could streamline grouping everything without turning it all into a table. I learned how to [jump to unique values](https://superuser.com/questions/873242/is-there-a-way-to-skip-down-to-the-next-change-in-value-in-excel) (start of 1, end of 1 or start of 2, end of 2 or start of 3... by highlighting column C and pressing CTRL + SHIFT + \. The only problem is that has to be done from the beginning every time. How can you highlight a column but in the middle? You can't! Okay it's faster to just copy the first 3 rows and add 1 to the leftmost row later.

I start compiling [list in another Excel sheet](https://user-images.githubusercontent.com/92915699/192112774-2bb7872b-45ae-4efc-9967-e6014b90abd5.png) that shows the series name, series number, and the rows associated with each one (25 in total).

For series 1-5, I wrote them all out. For 7, I thought, oh I could just copy and paste and still use the keyboard shortcut. but that spit me out to the beginning. So I just went through the whole thing again with the keyboard shortcut. By the time I got to 13, I decided to just manually scroll through the rows, spot new series numbers, and simply copy and paste the rows, and add 1 later to each number in the leftmost column. [Making progress on the table](https://user-images.githubusercontent.com/92915699/192112869-a447ff2d-f497-46c8-980b-703b19d32ebf.png).

Though I could easily pull down the formula to easily calculate the rest up to row 26, I had to delete the first row without compromising the latter. So I copied the new calculations and pasted into a new column, then replaced the calculation column so that I could safely delete the stuff in column A without causing errors.

Next step was to fill in column D "Row End" with the next row start minus 1, to get the [correct row end values](https://user-images.githubusercontent.com/92915699/192112978-a4a285fe-169f-446c-91c8-ec2d0624b33d.png). I had to type out "4940" for the last one, or else it was -1. Nuances of pulling through Excel calculations.

I had been doing this all in another sheet solely so that I could have windows side by side. This is way easier than navigating tab-to-tab within one sheet (I get lost easily and forget what I was doing). To keep a record of my work here, I insert the series number/row start/row end info as plain text in a new tab "Information". 

I did a random check with series 7 Samoa and series 22 Iceland to make sure the row start and ends are correct, and indeed they are. The series numbers all match up with where they are supposed to, so that is reassuring. You can see the product of my hard work in the right screen picture below.

Now that I know the "formulas" and have things set up, I tried to challenge myself to see if I could plot the rest of the 23 groups in the Sr-Nd plot in 5 minutes. My most efficient system involves working on two screens, where the [left screen is the large external monitor where the Excel action happens](https://user-images.githubusercontent.com/92915699/192113203-f8106b2a-11a7-4a9a-92ee-dabeeb2c3420.png) and the [right screen is my laptop, where the information is kept in sequential order](https://user-images.githubusercontent.com/92915699/192113194-212f9f7b-91c3-42f6-9cbb-748d87a3eed6.png)

That did not work. You can't really streamline manually adding a group to plot in the "select data" function. It's all one-by-one.

Yes, I am aware there is a data editor somewhere that allows me to make a plot through some kind of Excel code, but I am taking the simple way out today to make a point. Because of weird Excel copy/paste issues, I should write theses formulas in plain text and paste them one by one in the edit series maker. 

20 minutes later, I have made progress because I actually pre-wrote all the formulas on a separate notepad file to paste, one by one, into the Excel fields.

Urgh, why is this happening? All the Canary Island values are fine and not acidentally off by orders of magnitude...

![image](https://user-images.githubusercontent.com/92915699/192114551-13fc567e-4e99-4e03-9a4c-8d97bab4f705.png)

This is what happens when you plot Canary Islands alone...

![image](https://user-images.githubusercontent.com/92915699/192114580-2caae585-bb05-456a-a39c-5e2df56442d9.png)

I have no patience for this, so I deleted the Canary Islands. Usually I would stick with this longer, but I tried plotting this in a few different ways, but it might be some numbers/data property that I am not understanding. Apologies for removing this group.

This is the resulting Sr-Nd plot:

![image](https://user-images.githubusercontent.com/92915699/192114624-cce8a25e-48f9-43e6-822e-580f80329b8e.png)

## IgPet 

### Data

I copied and pasted all the data into a new sheet, and I made sure to have first column renamed to "Sample", and then include the JCode, KCode, and LCode columns to create the [working tab delimited text file](https://user-images.githubusercontent.com/92915699/192115066-12a28b2f-f954-4339-abcb-64a9ca26be75.png). I do not have symbols or legend codes figured out yet, but this should plot okay.

Conveniently, the excel file where I tracked the series number will be useful because I can actually make the legend very quickly in a [notepad file](https://github.com/thi-truong/thi-truong.github.io/files/9639530/Stracke2012-legend-1-to-25.txt), and I use those numbers as both KCode and JCode.

### Plotting

I go over to the MacBook which I always put to sleep, so turning it on takes about 10 seconds.

I have a Dropbox document folder synced up, though it's not the SAME IgPetDocs folder as on the Macbook, becuase I am still not sure how these things work. It's still an instantly transferrable file, even if I have some not-super-matching redundant folders.

I open IgPet, load the .txt file I just made, and make an X-Y plot where I select 87Sr/86Sr Nd first, and then 143Nd/144Nd second. I select the legend .txt file that I just made. I generate this in about a minute:

<img width="600" alt="Screen Shot 2022-09-24 at 12 29 16 PM" src="https://user-images.githubusercontent.com/92915699/192117835-e55e8966-4447-4f99-975a-ccec9024c629.png">

I also experiment with making plots that only show MORB, Hawaii, and the Austral-Cook endmembers. This requires a bit of self-referencing to know that 1 = Atlantic MORB, 2 = Pacific MORB, etc., but I have the numbers written out, so it is easy enough to reference. I use the [subselect tool](https://user-images.githubusercontent.com/92915699/192116689-b2e61ac6-c906-457c-b22d-8bab0b17db58.png), and this is the resulting Sr-Nd plot:

<img width="600" alt="Screen Shot 2022-09-24 at 12 33 29 PM" src="https://user-images.githubusercontent.com/92915699/192116656-ceac6661-eaf1-40b5-8134-d989bf22b207.png">

Next, I make the Pb-Pb-Pb plots. I have to refamiliarize myself with the process a bit, and I accidentally end up plotting 208Pb/206Pb the first time. It is easy enough to re-do. To show Austral-Cook endmembers better, I just select groups 23-25 and do not plot MORB here. My sequence is roughly:

* Subselect to match/include JCode = 23,24, 25
* Make X-Y plot with 206Pb/204Pb as the X and 207Pb/204Pb as the Y
* Go to Position, then Aspect, then make sure it is on "PortraitLower", since 207 is shown below 208 usually (hopefully I am not getting this reversed!). I changed the legend to be inside the diagram now, as it was now off the page.
* Save as pdf, select the "add last diagram + continue" option, which I think is actually worded confusingly. But it just means that the next time you click "save to pdf", it will be superimposed on whatever you last saved.
* Go to "New Y". Simply change the "Y" to 208Pb/204Pb. It will show the plot on top of the 207. Do not panic! Go to position again, then aspect, and then select "PortraitUpper". Now you shold see two plots with the same x-axis, one stacked on top of the other. Select "save as pdf" and choose the "last diagram + finish" option.

This is what you get as a result of the simple process:

<img width="627" alt="Screen Shot 2022-09-24 at 12 38 44 PM" src="https://user-images.githubusercontent.com/92915699/192115674-82f682f0-c09b-42cd-ba69-ab376e283075.png">

# Conclusion

How long did it take to make a Sr-Nd plot from Stracke et al. (2021)'s  supplementary table 1 with separate groups showing different symbol sizes?

**Microsoft Excel: 1.5 hours.**
**IgPet: 15 minutes**

Part the 1.5 hours in Excel was due to me familiarizing myself with Excel on Windows 11 and not knowing *all* the tips and tricks that one should probably know by now. My efforts to experiment made me more aware of some shortcuts, but I was still limited in my efficiency.

I often feel restricted in what I can do in Excel-- I have to use both mouse and keyboard, but they don't synchronize well. For example, while editing cells, you cannot use arrow keys or click in different areas of the sheet, unless you want to introduce chaos into every data range or calculation. So there is a lot of clicking, highlighting, copy and pasting, deleting that has to be done precisely and in separate steps. Quite tedious.

Now I am wondering how I could plot a different set of variables, like to make Pb isotope plots, in a streamlined way. I am thinking I'd have to work group-by-group yet again, and painstakingly replace the column letters to display new variables. It is just slightly less work than going through the entire Sr-Nd process again.

Some of the 15 minutes in IgPet is actually the time spent wrangling the 25 groups of samples and working in Excel. The actual IgPet plotting and exporting took maybe 5 minutes, and I did not alter any of the symbols, font size, design, etc. It's pretty much ready to edit in Illustrator. However, the plots were made quickly to demonstrate how quickly I could make them. These are hardly ready for presentations or publications. To make this work with my own research, the next step is to make sure all the column headers match with mine, or else IgPet won't plot them at the same time. This standardization process is next!
