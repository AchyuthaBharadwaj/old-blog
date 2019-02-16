---
title: "Linear, Logistic and Ridge Regression"
date: 2018-02-02
tags: [Machine Learning, Linear Regression, Logistic Regression, Ridge Regression]
excerpt: "Using linear, Logistic and Ridge regression to find the curve which best fits the data." 
mathjax: "true"
---

## Linear Regression

[link to repository](https://github.com/AchyuthaBharadwaj/Machine-Learning/tree/master/Simple%20Linear%2C%20Logistic%20and%20Ridge%20Regression)

Dataset from linRegData.npy. The data is a matrix (100, 2). Column 1 is $$x$$ and Column 2 is $$y$$. Data is be read using $$numpy.load(’linRegData.npy’)$$. Given a function $$y = f(x)$$, using linear regression a program to find the line which best fits the data. 

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/Intro-to-ML/Linear-Reg.png" alt="fitting linear curve"/>

## Ridge Regression

[link to repository](https://github.com/AchyuthaBharadwaj/Machine-Learning/tree/master/Simple%20Linear%2C%20Logistic%20and%20Ridge%20Regression)

Dataset from linRegData.npy. The data is a matrix (100, 2). Column 1 is $$x$$ and Column 2 is $$y$$. Data can be read using $$numpy.load(’linRegData.npy’)$$. For this exercise, fit a polynomial of degree 15 to the data using ridge regression. I.e. $$x$$ is converted to $$[1, x, x^2, x^3, . . . , x^{15}]^T$$. Using 5-fold cross validation, estimating the best $$λ$$ from the set, $$λ = [0.01, 0.05, 0.1, 0.5, 1.0, 5, 10]$$

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/Intro-to-ML/Ridge-Regression.png" alt="fitting a non-linear curve"/>

## Logistic Regression

[link to repository](https://github.com/AchyuthaBharadwaj/Machine-Learning/tree/master/Simple%20Linear%2C%20Logistic%20and%20Ridge%20Regression)

training a basic logistic regression classifier to classify two set of digits from the MNIST dataset. After preprocessing, the dataset loaded contains only digits 0 and 1. logReg.py implements logistic regression. The below plot shows training error vs. iterations.

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/Intro-to-ML/Logistic-Regression.png" alt="logistic regression"/>
