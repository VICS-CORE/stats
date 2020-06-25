---
layout: post
title: Training a 20 day forecaster
date:   2020-06-04
comments: true
hero: /assets/images/forecasting/hero2.jpeg
excerpt: The 10 day forecaster that we talked about in the previous post, allows us to predict only the next 10 days of Covid19 new cases by looking at the past 20 day trend. Greater the number of days that we can predict, the more is the time that we get to prepare for the future. Hence we enhanced our neural net to learn from 40 day trends and predict next 20 days.

---

For latest predictions, please visit our [tracker][tracker].

| Date | Predicted daily cases | Actual daily cases | Difference |
|:---:|:---:|:---:|:---:|
| Jun 5  | 8868  | 9851 | 983 |
| Jun 6  | 9082  | 9887 | 805 |
| Jun 7  | 9339  | 9971 | 632 |
| Jun 8  | 9933  | 9983 | 50 |
| Jun 9  | 10390  | 9987 | -403 |
| Jun 10 | 10820  | 9985 | -835 |
| Jun 11 | 11231 | 9996 | -1235 |
| Jun 12 | 11622 | 10956 | -666 |
| Jun 13 | 11675  | 11458 | -217 |
| Jun 14 | 11937  | 11929 | -8 |
| Jun 15 | 12509  | 11502 | -1007 |
| Jun 16 | 13060  | 10667 | -2393 |
| Jun 17 | 13213  | 10974 | -2239 |
| Jun 18 | 13456  | 12881 | -575 |
| Jun 19 | 13566  | 13586 | 20 |
| Jun 20 | 14060  | 14516 | 456 |
| Jun 21 | 14364 | 15413 | 1049 |
| Jun 22 | 14431 | 14821 | 390 |
| Jun 23 | 14835  | 14933 | 98 |
| Jun 24 | 15384  | 15968 | 584 |

![Predictions][chart]

Predictions last updated: 4 Jun

Data source: [OWID][owid]{:target="_blank"}

The 10 day forecaster that we talked about in the [previous post][prev_post], allowed us to predict only the next 10 days of Covid19 new cases by looking at the past 20 day trend. The look ahead window of 10 days is too small and we started with it as we had limited computing resources. Greater the number of days that we can predict, the more is the time that we get to prepare for the future. Hence we enchanced our neural net to learn from 40 day trends and predict next 20 days. As of now we don not have sufficient data to build any longer predictors. However that comes with a cost: the size of the network increases.

Let's revisit the concept of neural nets. A neural net is a universal approximator with learnable parameters called _weights_. That means, a neural network can be used to approximate any curve of the form `y = f(x)` provided some data points lying on the curve are known. This data is used to identify the relationship between x and y by figuring out the correct values of _weights_. That process is called _training_ the network.

When we try to predict larger trends by giving larger inputs and expecting larger outputs, the number of _weights_ in the network increases. In our case, when upgrading from a 10 day forecaster to a 20 day forecaster, the weights increase in number from 5170 to 27940. Consequently training time increases too. That means, it takes a lot more time to figure out the right combination of these _weights_ which will satisfy the relationship between x and y. 

Since we have access to limited resources at the moment, we couldn't refine the model as much as we would've liked to and hence it does not fit as well as the 10 day forecaster. Take a look at the comparison of the fit in the charts below. The top chart shows the 10 day predictions made everyday by the 10 day forecaster. And the bottom chart does the same for the 20 day forecaster.

![Fit comparison][comparefit]

The predictions of the 10 day forecaster made each day, fit very close the the actual cases (blue line), as against the 20 day forecaster, in which case, predictions don't align very well. 

However when we use the models to make predictions for a longer term (say a few months ahead), the 20 day forecaster does much better. The 10 day model predicts the peak too early which is very unlikely. Take a look at the peaks projected by both the models below. Top chart for 10 day model and bottom chart for 20 day.

![Peak comparison][comparepeak]

There are a few more standard techniques in deep learning to improve these forecasters. However we don't have enough resources at the moment to perform multiple simultaneous computations. Also, in a few more days, enough data would be available to build a 30 day forecaster as well. Please let us know in case you can arrange for a GPU enhanced computer for training these nets.

[chart]: {{ site.baseurl }}/assets/images/forecasting/chart4020.png
[comparefit]: {{ site.baseurl }}/assets/images/forecasting/comparefit.png
[comparepeak]: {{ site.baseurl }}/assets/images/forecasting/comparepeak.png
[prev_post]: {{ site.baseurl }}/2020/06/04/forecasting-covid19-cases.html
[tracker]: https://seva.ml/?utm_source=sevaml&utm_medium=Website&campaign=post&utm_content=4020
[owid]: https://ourworldindata.org/covid-cases?country=~IND
