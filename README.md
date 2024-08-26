# Zara Tzouros 
# About Me
I am a Data Manager at a large NHS organisation, specialising in Infection Prevention and Control and Microbiology. I am passionate about public health and using data science to improve patient care and outcomes.

Outside of work I enjoy being a mother to 3 exceptional sons, learning new languages, excercising, cooking and my number 1 guilty pleasure - Reading! I share the opinnion of George R.R. Martin wo said that “A reader lives a thousand lives before he dies . . . The man who never reads lives only one.” and I am keen to live thousands of lives, feel thousands of emotions and share those moments with others through the pages of a book! 

I am currently studying a data science apprenticeship degree with BPP universities and am thoroughly enjoying the challenge, this page details one my (non-work based) module projects. 

# Book Club Recommendations - Using Data Science 

# Introduction
'The best moments in reading are when you come across something – a thought, a feeling, a way of looking at things – which you had thought special and particular to you. Now here it is, set down by someone else, a person you have never met, someone even who is long dead. And it is as if a hand has come out and taken yours.' - Alan Bennett, The History Boys. 

This project analysed a book ratings and sales dataset and identified trends and relationships in the dataset. It uncovered valuable insights into reader preferences and market dynamics such as Fiction being the most popular genre and confirmed that there was a positive correlation between Author category and Average rating. The findings will be used to inform the book selections of a local reading club. 

# Method
Data was sourced from Kaggle and is available at:https://www.kaggle.com/datasets/thedevastator/books-sales-and-ratings 
The project aimed to identify:
1.	Top 10 highest rated books
2.	10 worst rated books
3.	Average rating distribution of all books
4.	Most popular genre of book
5.	If there is a correlation between author rating and average book rating (regression model)
6.	Which Publisher is dominating the book market
   
# Data Cleansing/ Preparation 
Formatting issues in titles were corrected. 
Book titles were translated into English to ensure that data visualization would be interpretable and easy to read by end users. 
Formatting issues in the Author column were corrected.

Cells that contained titles that could not be read were filled with the book title in English. This was done by searching by author/s and publication year. If the book titles could not be ascertained or there was dubious certainty (due to multiple author publications that year) the row was deleted. 

The Author column was also reviewed for completeness and accuracy, formatting issues (seen in figure 4 below) were corrected and missing authors were added to ensure data completeness. 

The Publication year was then reviewed to ascertain that there were no anomalies and that data fell within expected parameters:
![Year of original publication](https://github.com/user-attachments/assets/644026dd-82e2-4344-872c-830817bb09f6)

Figure 1: Year of orginal publication review

As evicenced by the graph above, it was initially assumed that there were issues with the publication dates, however on further interrogation it was established that negative numbers were ‘Before Common Era’(BCE) and positive numbers were ‘Common Era’ (CE) and were in fact accurate. 

There was duplication in the labelling of the categories used in the Genre column, both ‘fiction’ and ‘genre fiction’ were listed,  figure 6 below details how this was corrected. 

The language column was deleted as it added very little to the dataset, there were many missing values and several discrepancies between the book title language and publication language.

Conditional Formatting was used to identify duplicates. An example of this was, finding duplicate values in the Book Name column. Two different books shared the same name, so were incorrectly identified as duplicates and 1 of each duplicate was deleted, merging the dupplicates was considered but eventually discarded as publishers, author rating variation was not conducive to this.  

All other columns were reviewed and there was no other missing or inaccurate data identified. 

Blank cells where the book title could not be identified by author and publication year were deleted. 

Originally there were 1069 rows in the original dataset and 14 columns.99.06% of the original dataset remained after data cleansing and enrichment was performed. 

# Data Analysis
A combination of Microsoft Excel and SQL were used to manipulate the data, this was due to limited (but developing knowledge) of SQL and time management limitations. 
The Top 10 Books by highest average rating were identified using the ‘Order by’ function which return the results displayed in Figure 2 below. 

![Top 10 highest rated book](https://github.com/user-attachments/assets/7267b149-49f0-420d-83ad-921c94e96db8)

Figure 2: Top 10 highest rated books 

3 genres were identified from the dataset, using the syntax in Figure 2 below.

![Genres](https://github.com/user-attachments/assets/5f83364d-090b-4599-a672-a29d08e217ee)

Figure 3: Identifying the number of genres in the dataset

These were: Fiction, Non-fiction and Children which made up 83%, 16% and 1% of the dataset respectively. 

The histogram in Figure 4 below, has a symmetric, unimodal with a slight skewed left distribution as the mean (4.00) is less than the median (4.01).

![Distribution of Average Ratings](https://github.com/user-attachments/assets/d21d202c-e18d-4c8d-8ed9-a1e3fc27f021)

Figure 4: Distribution of Ratings Histogram

A logistic regression model was run in Microsoft excel which determined that there is a positive correlation between the category of author and average rating. To prepare the data for regression modelling the Author categories were classified as:

Novice	= 1

Intermediate = 2

Excellent = 3

Famous	= 4

This correlation was confirmed by the P value equalling less than 0.05 and the R squared value displayed a reasonable proportion of variance as can be seen in figure 3 below. 

![Regression Modelling Output](https://github.com/user-attachments/assets/f74bd21c-a688-4e59-91ed-e29cb5e91549)

Figure 5: Regression modelling output

Analysis of the gross sales, publisher revenue and Unit sold data was performed in Microsoft Excel using a pivot table, it was identified that Amazon is the leading market publisher, selling 59% of all units.
![The publishing market](https://github.com/user-attachments/assets/09d97074-ba73-46a5-b2c6-a054b4c43adc)

Figure 6: The Publishing Market: Sum of Units Sold, Sum of Gross Sales and Sum of Revenue by Publisher

# Results
The books listed in the graph below will be recommended to the book club, from which they can review and choose based on synopsis and genre etc.  

![Highest Average Rating Graph](https://github.com/user-attachments/assets/fe6586a8-78f9-490c-9913-4c9ec49db1e0)

Figure 7: Highest Average Rated Books

The books detailed in the graph below will be reviewed by the book club, with the recommendation they review a book as a means of critically reviewing the ratings system and to ascertain if the low rating is deserved.

![Lowest Rated Books Graph](https://github.com/user-attachments/assets/960d4b9e-72ac-42a3-9a9f-e279412247ab)

Figure 8: Lowest Average Rated Books 

Amazon Digital Services will be approached to ascertain if they currently offer NHS discount, or would be willing to offer a corporate discount. 

![Sum of Units sold by publisher](https://github.com/user-attachments/assets/d56bae16-f8ea-4277-81d8-838fda39e683)

Figure 9: Sum of Units Sold by Publisher

# Conclusion and Recommendations
This project and successfully identified trends and relationships in a book ratings and sales dataset. It uncovered valuable insights into reader preferences and market dynamics such as Fiction being the most popular genre and confirmed that there was a positive correlation between Author category and Average rating. From this data science project the following actions were taken:

•	The top 10 highest rated books will be recommended to the book club.

•	The lowest rated books will be discussed at the book club, as one book may be chosen to review if they deserved to be so poorly rated.

•	As the market leader, Amazon will be approached to ascertain if they offer NHS discount, or would be willing to offer a corporate discount.
