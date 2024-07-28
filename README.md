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

[Download here](https://github.com/user-attachments/files/16405334/Movies.Data.Homework.xlsx)


### Tools

 - Power Query - Data Cleaning Download here

 - Excel, Pivot Tables - Data Analysis, Creating reports and visualizations



### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:

 - Data loading and inspection.
 - Handling errors, missing values.
 - Data cleaning and formatting.


### Exploratory Data Analysis

 - Which genres were the most profitable these years?
 - Which actors were the most successful?...


### Results and Findings

The best profitable movie was: with Budget of... Box Office Revenue was 102,000,000 USD. The genre of this movie was...
The best actor was..
The best director was...

![Movie Data Dashboard](https://github.com/user-attachments/assets/172c60c1-9a9e-4daf-9fa2-b32c3752388b)

![Worst Movie](https://github.com/user-attachments/assets/f92c086f-3070-4dff-beb3-e8a39e7572ec)

![Best Prof Movie](https://github.com/user-attachments/assets/31ef7fcb-4ab7-4c28-ba7f-0cbe3eb67187)


#### M Language 

One of the interesting features I was working with was a specific code for Grouping in M language which enable me to Combine genres together for further analysis.

```
= Table.Group(#"Sorted Rows1", {"Movie Title"}, 

                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},

                                            {"AllData", each _, 

                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}

                                            }
```
