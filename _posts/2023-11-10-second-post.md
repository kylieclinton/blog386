---
layout: post
title:  "Marvel EDA Intro"
author: Kylie Clinton
description: An Intro to EDA of the Marvel API.
image: "assets/images/joel-muniz-yRQ6EL25vxU-unsplash.jpg"
--- 
## ~Introduction~
Exploratory Data Analyses(EDA) are interesting and informative ways to gather and understand data. There are many different ways to collect data to explore, such as APIs, web scraping, and finding established datasets. I wanted to do an EDA on a topic interesting to me with lots of insights to be gained. After searching for interesting data I could use, I found an API from Marvel that piqued my interest. I am not a comic book reader, but I have enjoyed the Marvel Cinematic Universe for the most part. Looking through what the API offered gave me some initial questions I decided to explore.

"What are the trends in character popularity within the Marvel Universe, and how have these trends evolved over time?"
"What insights can be gained regarding the changing popularity with different characters and events within the Marvel Universe?"

With these questions in mind, I dove into my EDA.

<img src="{{site.url}}/{{site.baseurl}}/assets/images/Marvel_Logo.svg.png" alt=""  style="width:600px;"/>/>

## ~Description~
Before this EDA began, I was a beginner to web scraping and making API requests. It took some time and some helpful Google searches to write my requests code, but in the end, I was able to get an inital dataset. I drew from the Characters endpoint of the Marvel API. Since my questions were focused around Character popularity, this seemed like the best option. To clean my data, I kept the columns with information I felt would be useful in my EDA while discarding the others. I also had to figure out how to best access all the data in nested dictionaries. The last step for me was to make sure any NaN's were changed to 0. This process created my first dataframe for my EDA.

I made another dataframe that drew from a list within the first dataframe showing the titles and years of the comics. I extracted the years from each and made my new dataframe show the Character's name followed by columns for each year Marvel has made comic books. If a character didn't have a comic in a year, I made sure the dataframe showed 0 instead of NaN after cleaning. The year columns a character had comics in were made to be counts instead of the name of the comic. This process concluded creating my second dataframe.

## ~Explanation~
Because of the nature of data collection, ethics needed to be taken into consideration. I checked the policy for Marvel's API usage to make sure I wouldn't violate any. I also made sure to take time and consider the purpose behind my EDA and that it was ethical. I made sure that the data I used would be protected through my API keys, which were included in my .gitignore file. I also wanted to make sure that the data I used would stay within the context in which it was meant for. No ethical lines were crossed during my EDA as it was taken into consideration throughout the process.

## ~Conclusion~
Finding, cleaning, and exploring the data collected in the Marvel API was an interesting process and a great learning experience. I was able to begin the process of answering my EDA questions and explore a topic I am interested in. Through coding and personal reflection, I was able to start assembling Avengers myself.

# Code and Data Links #
Here is the data: <a href= "https://github.com/kylieclinton/edaproject/blob/0db43d2e7688334e079df413c152c07b1b66e171/marvel.csv" target="_blank">Marvel Data</a>

Here is my code repository: <a href = "https://github.com/kylieclinton/edaproject.git" targer="_blank">Code Repository</a>
