---
title: Time series coffee chat
layout: post
categories:
- tech
---

I had coffee with a friend of mine before work today and we talked about some of the work he is doing around time series data analysis (he is working on a forecasting model for commodity prices). It's super interesting stuff and I want to write a note on some of the we discussed ideas here. Hopefully I'll get the chance to learn more about this too, which will probably lead to more posts.

### Identification

So when does a modelling problem become a time series problem? That is, when do you have to start considering the time element when trying to predict future values for data (or perform validation as I discuss below)? You can usually tell from visual inspection of the data, but one method is looking at the autocorrelation of the data points. This essentially measures how well correlated a data point is to the data shifted in time. I wanted to try doing this myself for stock price data (so unimaginative, forgive me). 

![acf](https://www.dropbox.com/s/5shmlkxbpzbeikl/autocorrelation.png?raw=1)

I downloaded Microsoft stock price data from Yahoo Finance. This plot can be generated in R with a really simple line of code `acf(msft$Value, plot=TRUE)`. The dashed blue line represents a 95% confidence interval. Given our autocorrelation is well above that interval for all lags, we can confidently say that the information is time-series. 

### Validation

<!-- Why not? why are you only able to regress with data after the training data? -->
When building models for time series analysis you can't use traditional cross-validation techniques (such as K-fold cross validation). This is because you are only able to validate with data that is lagging the training data. This [blog post](https://robjhyndman.com/hyndsight/tscv/) by Rob Hyndmann, who is a statistics professor at Monash, also talks about cross-validation techniques. At coffee we talked about two techniques: expanding and sliding window. 

#### Expanding window

Suppose we break our time-series data into some number (N) of equal sized chunks such that each represents some different time period. You can perform validation by using all of the data prior to validation set for training. That is the idea behind the expanding window method for time-series cross validation. Breaking the data up in this way gives you N - 1 sets of training and validation data. I think it's easier to understand this idea visually 

![rolling forecasting origin](https://robjhyndman.com/files/cv1-1.png)

I took this image straight from the blog post I linked earlier, which refers to this idea as "evaluation on a rolling forecasting origin". The points in the image, instead of referring to individual data points, can refer to sections of the training data. Rob's blog post presents the idea that you can also validate performance of your model with a chunk of data that is some number of steps ahead as well.

#### Sliding window

The sliding window approach follows the same principle as the expanding window one, except instead of taking all chunks of data prior to the validation set, you only take the chunk immediately before. I read a bunch of other blog posts (e.g. [this one](https://towardsdatascience.com/time-based-cross-validation-d259b13d42b8)) that suggest something similar, but for varying validation and training chunk sizes and smaller lags between the selected dataset. Other blogs call this time-series cross validation.