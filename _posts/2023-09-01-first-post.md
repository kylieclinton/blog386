---
layout: post
title:  "Tips and Tricks For Data Visualization"
author: Kylie Clinton
description: Compare different data visualization tools and pros/cons to each.
image: "assets/images/eberhard-grossgasteiger-zG8VFOg7wgo-unsplash.jpg"
--- 
## Introduction
Data visualization has taken the world by storm in recent years. Everyone wants their data to be presented in an engaging, easy-to-understand way. It allows us to analyze complex data, identify patterns, and extract valuable insights. It enables decision-makers to look at the simplified data and quickly make informed and accurate decisions. The boom in data visualization tools has made it easier for coders and non-coders alike to present data in a visually appealing way.

This tutorial will focus on three of those tools and compare setup, syntax, and results so you can decide which tools you would like to use. The three I will be focusing on are python packages Matplotlib and seaborn, R package ggplot2, and Tableau. For this tutorial, I will be using the [World Instant Noodles Consumption 2022]([https://statistics.byu.edu](https://www.kaggle.com/datasets/fortuneuwha/world-instant-noodles-consumption-2022/)) dataset.
## Python
Python has several packages developed to make data visualization easier. Two of the most popular are Matplotlib and Seaborn. Matplotlib is the base-level package for data visualization in python. It is highly customizable, can have a steep learning curve, and primarily makes static plots but can also do interactive plots.

Seaborn is built on top of Matplotlib and makes more aesthetically pleasing plots. It specializes in statistical plotting and works seamlessly with Pandas dataframes. It also simplifies the process of making visualizations and quickly generates informative statistical plots.

Using the dataset above, we can use these packages to create appealing data visualizations.

### Step 1: Import Libraries and Load the Data
Before loading the data, make sure you have the proper packages installed by running this code into your terminal.

```
pip install matplotlib seaborn pandas
```

Once your packages are installed, you can load the data in python.

```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv("noodles.csv")
```

### Step 2: Prepare the Data
Preparing your data is important before making visualizations. This step can include cleaning data, sorting it, removing duplicates, and making data types consistent. In this example, we will select the top 10 countries after sorting the data in descending order.

```
top_10_countries = data.sort_values(by='2022', ascending=False).head(10)
```

### Step 3: Create a Bar Plot and Box Plot
To make the bar plot, follow the code below:

```
plt.figure(figsize=(12, 6))
sns.barplot(x='2022', y='Country/Region', data=top_10_countries, palette='viridis')
plt.title('Top 10 Countries with Highest Instant Noodles Consumption (2022)')
plt.xlabel('Consumption (Billion Servings) in 2022')
plt.ylabel('Country/Region')
plt.grid(axis='x')
plt.show()
```
![top_10_countries_bar]({{github.com.kylieclinton/blog386}}/{{[site.baseurl](https://kylieclinton.github.io/blog386/)}}/assets/images/top_10_countries_bar.png)

To make the box plot, follow the code below:

```
plt.figure(figsize=(10, 6))
sns.boxplot(x='2022', data=top_10_countries, color='royalblue')
plt.title('Box Plot of Instant Noodles Consumption (2022) for Top 10 Countries')
plt.xlabel('Consumption (Billion Servings) in 2022')
plt.grid(axis='x')
plt.show()
```
![top_10_countries_box]({{github.com.kylieclinton/blog386}}/{{[site.baseurl](https://kylieclinton.github.io/blog386/)}}/assets/images/top_10_countries_box.png)

To save your plots as a .png or other filetype, you can use the following code:

```
plt.savefig('top_10_countries_bar.png', format='png')
plt.savefig('top_10_countries_box.png', format='png')
```
