---
layout: post
title:  "Marvel EDA"
author: Kylie Clinton
description: An EDA of the Marvel API.
image: "assets/images/erik-mclean-8SeJUmfahu0-unsplash.jpg"
--- 
## ~Introduction~
The Marvel Api provides insights into the Marvel Comic Universe and its characters. The data contains answers to several questions I found when looking at the API general information. My previous post <a href="https://kylieclinton.github.io/blog386/2023/11/10/second-post.html" target="_blank">Marvel EDA Intro</a> discussed in more detail my motivation behind the questions I developed and why I chose this dataset. To paraphrase, I grew up enjoying Marvel movies and was curious how the comics would affect movie production. I was also curious about popular characters and how popular they have been in comics over time. The questions I formed were as follows:
 - What are the trends in character popularity within the Marvel Universe, and how have these trends evolved over time?
 - What insights can be gained regarding the changing popularity with different characters and events within the Marvel Universe?

The rest of this post delves into my findings from my exploratory data analysis (EDA).

## ~Findings~

Before getting into my insights from my EDA, <a href="https://github.com/kylieclinton/edaproject.git" target="_blank">here</a> is a link to my GitHub repository with the data and .ipynb file with the code I wrote.

To answer my questions, I cleaned and manipulated the data from the [Marvel API](https://developer.marvel.com/). I made three dataframes, one with the uncleaned data, one with the cleaned data, and one with extracted data for time analysis. I used the latter two dataframes in my EDA. The cleaned dataframe gave rows of character names, values for comic, story, and event mentions, and lists of the comics, stories, and events where the character is mentioned. The manipulated data extracted years from the comics list, creating the new dataframe with character names, the years, and values for mentions in each year.

The visualizations I made helped to answer my questions more clearly. The first ones I made were bar graphs from the cleaned dataset. I wanted insights into how frequently the original Avengers Characters were mentioned throughout comics, and I wanted the same for the top 10 most popular characters.
<img src="{{site.url}}/{{site.baseurl}}/assets/images/og_avengers.png" alt="Data Viz" style="width:600px;"/>

For my Avengers visualizations, the most popular character mentions were for Iron Man and Captain America. That wasn't surprising for me as they are some of the most common Marvel Characters I knew growing up. The movies and shows with those characters also proved to me that they are the most popular Avengers from the original comic group.

<img src="{{site.url}}/{{site.baseurl}}/assets/images/top_10.png" alt="Data Viz" style="width:600px;"/>

For the Top 10 Characters Story mentions, I needed to run a sort on the data. When the bar graph appeared, I wasn't surprised by the results. From my personal knowledge, Peter Parker as Spider-Man has had more movies and shows and comics (according to the data) than other superheroes. I have heard more debates over which actors played Peter Parker best than other characters. His popularity in the comics wasn't surprising to me. There was more I wanted to learn about Spider-Man's presence in Marvel comics over time and how his various characters changed comic frequency.

The Spider-Man character and the variations like Spider-Girl and Spider-Ham in the data carried its own interesting insights. Since the Peter Parker Spider-Man was dubbed the most popular Marvel character according to how many stories mention him, I wanted to see when his character appeared and how many comics he has appeared in over time. I wanted to see how his popularity has evolved over time. The resulting time plot was shocking but very interesting. I plotted the cumulative sum of the number of comics mentioning Spider-Man or variants. When the line flattens shows no increase in total mentions.

<img src="{{site.url}}/{{site.baseurl}}/assets/images/spiderman_time.png" alt="Data Viz" style="width:1100px;"/>

As time continues there are more Spider-Man characters being written. The popularity surrounding this character seems to continue to increase. The only stagnant parts of Spider-Man's comic book popularity is shortly after he came out as a character in 19623, from 1964 to 1982 and 1983 to 1989. After 1989 the number of Spider-Man comics or comics with the character has skyrocketed. It's no wonder he is the most popular character.

As an additional part of my EDA, I wanted to see what numbers Peter Parker as Spider-Man had for mentions. Below shows what the code returned.
```
print(f"Marvel Character appearing in most stories and comics:\nName: {df_sorted['name'].iloc[0]}\nComics: {df_sorted['comics_available'].iloc[0]}\nStories: {df_sorted['stories_available'].iloc[0]}\nTotal Mentions: {top_10_characters['Spider-Man (Peter Parker)'].cumsum().iloc[-1]}")
```

```
Marvel Character appearing in most stories and comics:
Name: Spider-Man (Peter Parker)
Comics: 4402
Stories: 6385
Total Mentions: 19
```

<img src="{{site.url}}/{{site.baseurl}}/assets/images/current_mentions.png" alt="Data Viz" style="width:300px;"/>

<img src="{{site.url}}/{{site.baseurl}}/assets/images/of_avengers_time_2.png" alt="Data Viz" style="width:1100px;"/>



<img src="{{site.url}}/{{site.baseurl}}/assets/images/og_avengers_time.png" alt="Data Viz" style="width:1100px;"/>





<img src="{{site.url}}/{{site.baseurl}}/assets/images/top_10_mentions.png" alt="Data Viz" style="width:300px;"/>

<img src="{{site.url}}/{{site.baseurl}}/assets/images/top_10_time.png" alt="Data Viz" style="width:1100px;"/>

## ~Summary~


## ~Conclusion~
