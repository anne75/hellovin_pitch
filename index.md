---
title       : Wine Guess Game
subtitle    : What is it ? How it works ?
author      : anne75
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## What is it ?

The wine Guess Game is a very simple prediction game.  

The player should (or pretend to) have a glass of red wine in hand.
By looking at it and smelling it, he/she assesses the levels of:      
 - tannins   
 - spice   
 - aromas  
present in the wine.

Then the player enters those levels on the app by the use of sliders.

The algorithm predicts which wine the player has in hand and plots where it comes from.

---

## The data

The data used for the prediction comes from the ` FactoMiner ` package. 

It is a  small dataset of dimentions 21x31.

It is limited to 3 wine appellations among the Loire valley red wines:   
 - Bourgueil   
 - Chinon   
 - Saumur  

Those appellations have strict requirements in term of geographical origin.

---

### Here it is represented:   


<img src="assets/fig/unnamed-chunk-2.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

Terroir is a very serious topic, regulations impose a geographical origin. So data was downloaded from the [French open data website](http://www.data.gouv.fr/) to obtain and plot them

---

## The Algorithm

The emphasis was put on user-friendliness.
A very simple tree was chosen, as to select a limited number of attributes the player would have to enter.

This is the result of the tree:   
![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3.png) 

---

## Have fun

From the tree presented above:   

  - You have a Saumur if you have more tannins and spices.   
  - You have a Bourgueil if you have low tannins but high aromas.   
  - You have a Chinon if you have a complex smell.   

If you are curious, here are some details about the tree:   

```
## 
## Classification tree:
## tree(formula = label ~ ., data = vin, control = tree.control(minsize = 1, 
##     nobs = 21))
## Number of terminal nodes:  6 
## Residual mean deviance:  0 = 0 / 15 
## Misclassification error rate: 0 = 0 / 21
```
