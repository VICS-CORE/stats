---
layout: post
title: Has India Peaked Yet?
date:   2020-05-01

---
Recently, Data Driven Innovation lab (DDI) at Singapore University of Technology and Design (SUTD) came out with an [implementation][sutd-paper]{:target="_blank"} of the popular SIR model and tried to predict the COVID-19 peak dates for various countries including India. They predicted that India would peak on 20th April and 97% of the expected cases would have been identified by May 25th. We were curious to verify these dates and built a methodology to validate these predictions. 

Our method has a limitation that it can confirm the peak only 3 days after the actual peak date. After running our calculations, we find that the predictions are incorrect for most of the countries in the rising half of the epidemic, where new highs are still being reported. The details of our analysis are presented [here][paper]{:target="_blank"} and our calculations and code is available in this [notebook][notebook]{:target="_blank"}.

It is still not confirmed that India has peaked, 10 days after the predicted peak date and the actual date does not appear to be any time soon as per our calculations So it is highly unlikely that 97% of expected cases would end by the forecast date for countries such as India, Pakistan, Saudi Arabia, UAE.. Further we predict that the daily new cases will never become zero as predicted by this paper but will leave behind an asymptote.

### Logic

We use calculus to identify the peak. A peak on the epidemic curve (i.e. new patients per day) is a maximum. To identify maxima and minima on a curve, we use the fact that first order derivative becomes zero at that point. So we calculate change in daily cases which denotes the `slope` of the curve and identify dates where this curve becomes 0. Each point is a potential peak. 

However, we find multiple such points since the derivative becomes 0 whenever the curve is parallel to x-axis. To further verify that it is a true peak, we cross examine the second order derivative. At maximums, the second derivative, i.e. `change in slope`, should be negative because the slope changes from positive to negative at a peak.

![Derivative Diagram][derivative]

### Peak dates

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

### Graphs

Following is the list of charts for the countries mentioned above. For each country, there are three timeseries charts that have been plotted. First shows the cumulative number of confirmed cases. Second is the epidemic curve, i.e. frequency of new patients per day. Third denotes the first order derivative of the epidemic curve, i.e. the change in daily cases. It is useful for finding peaks.

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


[sutd-paper]: https://ddi.sutd.edu.sg/when-will-covid-19-end/
[notebook]: https://github.com/VICS-CORE/stats/blob/master/02_Total_daily_slope.ipynb
[paper]: https://www.google.com

[in_chart]: ../../../assets/images/02/india.png
[cn_chart]: ../../../assets/images/02/china.png
[sk_chart]: ../../../assets/images/02/south_korea.png
[us_chart]: ../../../assets/images/02/united_states.png
[br_chart]: ../../../assets/images/02/brazil.png
[uk_chart]: ../../../assets/images/02/united_kingdom.png
[it_chart]: ../../../assets/images/02/italy.png
[es_chart]: ../../../assets/images/02/spain.png
[de_chart]: ../../../assets/images/02/germany.png
[fr_chart]: ../../../assets/images/02/france.png
[pt_chart]: ../../../assets/images/02/portugal.png
[ae_chart]: ../../../assets/images/02/united_arab_emirates.png
[sa_chart]: ../../../assets/images/02/saudi_arabia.png
[pk_chart]: ../../../assets/images/02/pakistan.png

[derivative]: ../../../assets/images/02/derivative.jpg