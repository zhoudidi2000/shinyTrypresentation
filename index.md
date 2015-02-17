---
title       : Predict your kid's height
subtitle    : 
author      : Di Zhou  Feb. 16, 2015
job         : 
logo        :
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

   In the Victorian era, Sir Francis Galton showed that "when dealing with the transmission of stature from parents to children, the average height of the two parents, ...is all we need care to know about them"(1886).

   The shinyTry app is an application where you can use to predict your kid's height according to your and your partner's height.

--- .class #id 

## How to use

There are 2 options you can use this app.
   1. If you know R:
      Put server.R and ui.R files together in a folder(you can name the folder yourself, eg. shinyTry). Install **Shiny** package by `install.packages("shiny")`, and load it using `library(shiny)`. Run the application using `runApp(<path/foldername>)`. You will see the application in a browser. Follow the instructions to use the application. 
      
   2. RStudio hosts service for Shiny apps. So you can use the app at: [https://zhoudidi2000.shinyapps.io/ShinyTry2/](https://zhoudidi2000.shinyapps.io/ShinyTry2/).

---
## More information

Height is a classical example of an inherited human trait. Research showed mid-parental prediction method explained 40% of the sex- and age-adjusted height variance. So this application only contributes 40% of the influence to children's height, other factors might be race, nutrition, activities, region and so on...

---     
## Behind this App

   This prediction is based on the linear regression analysis method using the data from Galton in 1885. Generally, The midparent's height is an average of the fathers height and 1.08 times the mother's. We used the dataset to build an algorithm, and the user use the midparent's height to predict their children's height.

```
## (Intercept)      parent 
##  23.9415302   0.6462906
```
So the model is: kid's height = 23.94+(Father's height+mother's heightX1.08)/2X0.646

