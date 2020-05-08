---
layout: page
permalink: /papers/cpec
title: Confirming Peak of the Epidemic Curve (CPEC) for COVID-19 pandemic
comments: true

---
\- Mayank Bhagya & Radhesh Mohandas

### Abstract

Various models are being proposed to predict the peak dates of the Covid-19 Pandemic. It is difficult to propose a suitable model as it is difficult to collect data standardised and accurately across international borders inmidst of this emergency. There is a need to verify the events predicted by these models to understand their veracity. So we built a methodology to verify these predictions independently. Responsive actions from various governments and the social behaviour of it's citizens also changes the course of the disease spread in a big way and these predictions have to be progressively adapted from real data. For India, where there was swift action from the administration, the epidemic is under check but given the size and diversity of the population it is very difficult to predict the disease progression. Our work concludes that no predicted peak date for India has come true.


### Introduction

An epidemic curve shows the distribution of newly infected cases as a bell curve. A peak on that curve is the day when the highest number of individuals are found to be infected and post that date, the frequency is reduced. Predicting the peak is of significance since it indicates the maximum number of infected patients requiring medical care at the same time. It can help the administration to prepare the healthcare system and also estimate on when the epidemic might end. There are many models to predict the peak date and the most popular ones for the Covid-19 Pandemic are SIR and its variants. In this study, we have built up a methodology to confirm the peak dates predicted by any such model.

Recently, Data Driven Innovation lab (DDI) at Singapore University of Technology and Design (SUTD) came out with an [implementation][sutd_paper] of the SIR model and tried to predict the Covid-19 peak dates for various countries. 

Similarly, Institute for Health Metrics and Evaluation (IHME) at University of Washington (UW) has come up with it's [models][uw_paper] which declare peaks for select American and European countries.

We'll verify whether the peak dates provided by these two models are correct or not.

### Methodology

#### Overview

We've used basic calculus in order to identify peaks in a given curve. Peaks of a curve are maximas and we need to find the global maximum in order to correctly identify the peak. Hence we identify points where the slope of the epidemic curve crosses 0. The points thus identified can be any of maxima, minima or points of inflexion. To accurately declare a point as a maximum, we've used the second order derviative of the curve. Once we ensure that the points selected are maxima only, we finally choose the point with maximum average number of cases and declare it as the peak.

#### Identifying points where slope is 0

The slope of the epidemic curve is given by change in daily number of cases. Order of these numbers vary from location to location. Hence we've normalised this data by converting it to percentiles. The day with maximum daily cases is considered as 100%. Next, since `number of new cases` is a discrete variable with highly varying numbers each day, the plot of percentiles varies equally and is not smooth. In order to minimize noise and identify a trend, we first compute a six day centered moving average of the daily number of cases. More days in the moving average would mean a smoother curve but would be at the cost of the days that we need to wait to confirm the peak date after it truly happens. Next, slope of this moving average curve at any given date is calculated by subtracting the value three days before that date from the value three days after that date and averaging the difference by a factor of 6. This denotes the change in daily new cases per day and its arctangent gives the slope of the smoothened curve. We identify the dates where sign of this slope changes and declare them as potential peaks. Smoothening the curve does not alter the veracity of the disease spread direction as the data collected is mostly the date the cases were reported which have a lag and very across data sets.

#### Verifying whether a potential peak is a maximum

In order to distinguish between maxima, minima and points of inflexion, we use the second order derivaitve. At maxima, the slope of the curve changes from negative to positive and at minima, the slope changes from positive to negative. At points of inflexion, the slope hits 0 but again continues in the same direction. With this knowledge, we compute the slope of slope, i.e. the derivative of derivative at all potential peaks and check its sign. The values of slope form a curve which is also rough and can benefit from smoothening. Hence we calculate a six day centered moving average of the slope and evaluate its sign on each potential peak. We reject all dates where second order derivative is 0 or positive. Remaining points are maxima for sure.

#### Choosing one out of many maximums

While ideally the epidemic curve should resemble a bell shape, real data plots can vary significantly because of govt intervention, change in people behavior, climate et cetera. This can result in multiple maxima in the curve. In such situations, we consider the day with greater number of new patients as the peak. An example for the same is United States.

#### Algorithm

1. % new cases at any date d = 100 * new cases at date d / max(new cases)
2. smoothened new cases = centered 6 day moving average of % new cases
3. change in new cases at date d = ( smoothened new cases at d+3 - smoothened new cases at d-3 ) / 6
4. slope at date d = arctangent (change in new cases at date d)
5. potential peaks = dates where slope changes sign
6. change in slope = ( slope at date d+1 - slope at d-1 ) / 2
7. maximums = potential peaks where change in slope is negative
8. peak = maximum with greater % new cases

### Results

#### Peak dates

The table below shows a comparison of peak dates as per our study and Singapore University's study.

| Country | Our verification | SUTD |
| ------- | ---------------- | ---- |
| India | Peak not hit | 20 Apr |
| China | 13 Feb | 08 Feb |
| South Korea | 02 Mar | 02 Mar |
| United States | 09 Apr | 10 Apr |
| Brazil | Peak not hit | 21 Apr |
| United Kingdom | 12 Apr | 12 Apr |
| Italy | 25 Mar | 29 Mar |
| Spain | 01 Apr | 02 Apr |
| Germany | 02 Apr | 01 Apr |
| France | 01 Apr | 03 Apr |
| Portugal | 11 Apr | 06 Apr |
| United Arab Emirates | Peak not hit | 27 Apr |
| Saudi Arabia | Peak not hit | 27 Apr |
| Pakistan | Peak not hit | 27 Apr |

#### Graphs

Following is the list of charts for the countries mentioned above. For each country, there are three timeseries charts that have been plotted. First shows the cumulative number of confirmed cases. Second is the epidemic curve, i.e. frequency of new patients per day. Third denotes the first order derivative of the epidemic curve, i.e. the change in daily cases. It is useful for finding peaks, which are denoted by vertical red lines in the second and third chart.

| ![India][in_chart] |
| ![China][cn_chart] |
| ![South Korea][sk_chart] |
| ![United States][us_chart] |
| ![Brazil][br_chart] |
| ![United Kingdom][uk_chart] |
| ![Italy][it_chart] |
| ![Spain][es_chart] |
| ![Germany][de_chart] |
| ![France][fr_chart] |
| ![Portugal][pt_chart] |
| ![United Arab Emirates][ae_chart] |
| ![Saudi Arabia][sa_chart] |
| ![Pakistan][pk_chart] |

### Conclusion

We find that the dates predicted by UW are correct and may have an offset of a day or two for the reasons stated above. The dates predicted by SUTD are also verified for the countries that have clearly passed the peak. But for the countries which are still in the rising half of the epidemic, the dates predicted are incorrect in most of the cases.

### References



[sutd_paper]: https://www.altaveu.com/documents/covid19predictionpaper20200426.pdf
[uw_paper]: https://covid19.healthdata.org/

[in_chart]: {{ site.baseurl }}/assets/images/02/india.png
[cn_chart]: {{ site.baseurl }}/assets/images/02/china.png
[sk_chart]: {{ site.baseurl }}/assets/images/02/south_korea.png
[us_chart]: {{ site.baseurl }}/assets/images/02/united_states.png
[br_chart]: {{ site.baseurl }}/assets/images/02/brazil.png
[uk_chart]: {{ site.baseurl }}/assets/images/02/united_kingdom.png
[it_chart]: {{ site.baseurl }}/assets/images/02/italy.png
[es_chart]: {{ site.baseurl }}/assets/images/02/spain.png
[de_chart]: {{ site.baseurl }}/assets/images/02/germany.png
[fr_chart]: {{ site.baseurl }}/assets/images/02/france.png
[pt_chart]: {{ site.baseurl }}/assets/images/02/portugal.png
[ae_chart]: {{ site.baseurl }}/assets/images/02/united_arab_emirates.png
[sa_chart]: {{ site.baseurl }}/assets/images/02/saudi_arabia.png
[pk_chart]: {{ site.baseurl }}/assets/images/02/pakistan.png
