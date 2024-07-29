# Movie Data Analysis Dashboard





## Table of Content

 - [Project Overview](#project-overview)

 - [Data Sources](#data-sources)

 - [Tools](#tools)

 - [Data Cleaning/Preparation](#data-cleaning-/-preparation)

 - [Exploratory Data Analysis](#exploratory-data-analysis)

 - [Findings and Findings](#results-and-findings)

 - [M Language](#m-language)



### Project Overview

This data analysis project aims to provide insights into the performance and trends of movies from 2012 to 2016. 

By analyzing various aspects of the movie data, we seek to identify patterns, make data-driven recommendations, and gain a deeper understanding of the industry's dynamics.



### Data Sources

Movie Data: 

The primary dataset used for this analysis is the "Movie Data Homework.xmls" file, containing detailed information about each movie's performance, actors, directors, etc.

[Download here](https://github.com/user-attachments/files/16406210/Movies.Data.xlsx)


### Tools

 - Power Query - I used Power Query for Data Cleaning 

 - Excel, Pivot Tables - I used them for Data Analysis, Creating reports and Visualizations



### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:
 - Data loading and inspection.
 - Handling errors, missing values.
 - Data cleaning and formatting.
The Excel file after the data cleaning and preparation process can be  downloaded here - [Dashboard](https://github.com/user-attachments/files/16406211/Movies.Data.Ready.for.Dashboard.xlsx)


### Exploratory Data Analysis

 - Which genres were the most profitable these years?
 - Which actors were the most successful?
 - Which movie had the biggest Budget?
 - Which movie was the most profitable these years?
 - Which movie was the most unprofitable these years?


### Results and Findings

  The best profitable movie was: "The Devil Inside" with a Budget of 1,000,000 Box Office Revenue was 102,000,000 USD. The genre of this movie was "Horror".
  
  The best actor was Jennifer Lawrence.
  
  The best director was Chris Renaud.
  
  The best genre was Action.
  
  The best movie by Box Office Revenue was Despicable Me 2.
  
  The best movie by budget was "The Hobbit: The Battle of the Five Armies". 

  
 
  ![Movie Data Dashboard](https://github.com/user-attachments/assets/01b260c9-57fb-4b7b-b511-90db817f2627)



#### M Language 

One of the interesting features I was working with was a specific code for Grouping in M language which enable me to Combine genres together for further analysis.

```
= Table.Group(#"Sorted Rows1", {"Movie Title"}, 

                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},

                                            {"AllData", each _, 

                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}

                                            }
```
