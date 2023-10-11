---
layout: post
title:  "Tips and Tricks For Data Visualization"
author: Kylie Clinton
description: Compare different data visualization tools and pros/cons to each.
image: "assets/images/eberhard-grossgasteiger-zG8VFOg7wgo-unsplash.jpg"
--- 
## Introduction
Data visualization has taken the world by storm in recent years. Everyone wants their data to be presented in an engaging, easy-to-understand way. It allows us to analyze complex data, identify patterns, and extract valuable insights. It enables decision-makers to look at the simplified data and quickly make informed and accurate decisions. The boom in data visualization tools has made it easier for coders and non-coders alike to present data in a visually appealing way.

![Data Viz](/assets/images/lukas-blazek-mcSDtbWXUZU-unsplash.jpg)

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
import pandas as pd # loading pandas
import matplotlib.pyplot as plt # load plotting packages
import seaborn as sns # loading seaborn packages for plotting

data = pd.read_csv("noodles.csv")
```

### Step 2: Prepare the Data
Preparing your data is important before making visualizations. This step can include cleaning data, sorting it, removing duplicates, and making data types consistent. In this example, we will select the top 10 countries after sorting the data in descending order.

```
top_10_countries = data.sort_values(by='2022', ascending=False).head(10)
```

### Step 3: Create a Bar Plot and Box Plot
Before making the plots, note that python has various colors and palettes to choose from for further customization. Additionally, you can save your plot as a value, but it might require some minor code changes. To make the bar plot, follow the code below:

```
plt.figure(figsize=(12, 6))
sns.barplot(x='2022', y='Country/Region', data=top_10_countries, palette='viridis')
plt.title('Top 10 Countries with Highest Instant Noodles Consumption (2022)')
plt.xlabel('Consumption in 2022')
plt.ylabel('Country/Region')
plt.grid(axis='x')
plt.show()
```
![Bar Plot](/assets/images/top_10_countries_bar.png)

To make the box plot, follow the code below:

```
plt.figure(figsize=(10, 6))
sns.boxplot(x='2022', data=top_10_countries, color='royalblue')
plt.title('Box Plot of Instant Noodles Consumption (2022) for Top 10 Countries')
plt.xlabel('Consumption in 2022')
plt.grid(axis='x')
plt.show()
```
![Box Plot](/assets/images/top_10_countries_box.png)

To save your plots as a .png or other file type, you can use the following code:

```
plt.savefig('top_10_countries_bar.png', format='png')
plt.savefig('top_10_countries_box.png', format='png')
```

## R
R is a great tool for data scientists. It is built to interpret data graphically, making it easy to create visualizations with the programming language. R has a base graphical library loaded to make visualizations simply, but this tutorial will focus on one of the optional libraries, ggplot2. Ggplot2 is a coherent system for building and describing graphs. The syntax can be longer than the base R graphics, but it gives more room for creativity and aesthetics. To show the similarities and differences in making visualizations in python vs. R, the below steps will show how to make the same kind of graphs as above in python.

### Step 1: Load Libraries and Data
Just as in python, we need to start by loading the libraries we need to make our graphs, and loading the data. The dplyr library makes syntax more straightforward to use, and ggplot2 will help us make our graphs.
```
library(ggplot2) # graphics package
library(dplyr) # consistent and clear syntax

data <- read.csv("noodles.csv")
```
### Step 2: Filter the Data
Once the data is loaded, we need to filter our data. To do this, we will use the %>% or 'pipe' symbol so we don't have to run different lines of code and they can run together.
```
top_10 <- data %>%
  arrange(desc(`2022`)) %>% # arrange data in descending order by the 2022 variable
  head(10)
```

### Step 3: Create the Bar and Box Plots
In R, it is best practice to save plots and graphs as values to reference later. The same can be done in python. R has a variety of colors and themes to choose from to further customize your visualizations. Below is the code to make the bar and box plots. Note: when loading data into R, sometimes symbols in variable names will change. Make sure to look at your data before listing variables to best avoid errors.

Create the Bar Plot:
```
bar_plot <- ggplot(top_10, aes(x = reorder(`Country/Region`, -`2022`), y = `2022`)) +
  geom_bar(stat = "identity", fill = "skyblue") +
  labs(title = "Top 10 Countries with Highest Instant Noodles Consumption (2022)",
       x = "Country",
       y = "Consumption") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
print(bar_plot)
```
![Bar Plot](/assets/images/top_10_countries_bar_r.png)

Create the box plot:
```
box_plot <- ggplot(top_10, aes(y = `X2022`)) +
  geom_boxplot(fill = "royalblue") +
  labs(title = "Instant Noodles Consumption (2022) for Top 10 Countries",
       x = "Country",
       y = "Consumption") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1)) + coord_flip()
print(box_plot)
```

![Box Plot](/assets/images/top_10_countries_box_r.png)

When saving plots from R as a file, you can customize the size and file type. To save your plots, use the following syntax:
```
png("top_10_countries_bar.png", width = 800, height = 400)
print(bar_plot)

png("top_10_countries_box.png", width = 800, height = 400)
print(box_plot)
dev.off()
```

## Compare and Contrast


## Conclusion
