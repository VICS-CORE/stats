---
layout: post
title: Prediction of India's Covid-19 growth using a Neural Network (AI)
date:   2020-05-11
comments: true

---

On April 26th, we analysed the number of new cases per day and built a model to estimate the rate at which covid-19 cases will grow in India. The following curve shows the number of new cases per day as of Apr 26th:

|Daily new cases as of Apr 26th|
|:---:|
|![New cases per day][daily_chart]|

According to [this report][incubation], most COVID19 patients take about 5 to 12 days to develop symptoms. This is known as _incubation period_. This implies, if a lockdown happens today, the number of cases will start reducing only after at least 5 days. Lockdown 1.0 started in India on Mar 24th. We looked at the actual data and found that the rate of infection started coming down only after April 5th. It took 11 days to show results on ground.

Neural Network is an Machine Learning Algorithm which works on Artificial Intelligence. It looks at some data (called as training data), learns from it and then can predict what would happen after that. No prediction is perfect but this model has a scientific basis to it and has been found my scientists to be quite helpful in many a cases. We picked this algorithm for curve fitting.
After the effects of lockdown started showing, we trained our model using 21 days' data, i.e. Apr 5th to 26th. This would capture the behaviour of growth rate in a lockdown mode. So it should predict the growth accurately as long as the lockdown continues and 5-10 days thereafter.

In the following plot, the line in red denotes actual growth rate numbers from Apr 5th to 26th and the blue line denotes the projected numbers. Since the Lockdown 2.0 was extended till May 3, we can expect the predictions till May 13th to be accurate as per this algorithm.

|Our model|
|:---:|
|![Our model][nn_chart]|

As it can be seen, the growth rate stagnates at about 7%. We used this information to plot the cumulative number of cases by date.

|Projected cumulative cases|
|:---:|
|![Projected cumulative cases][total_chart]|

According to this model, the cumulative number of infections rises to 50,000 after first week of May, which has held true. It predicts the number touching 1,00,000 around May 15th. 

We ran the algorithm again with training data till May 11th and here is the new curve. It agrees/disagrees with the earlier curve but the growth rate now stagnates around 8%.

|Updated model|
|:---:|
|![Projected Growth Rate][may11_nn_chart]|

As it can be seen, the growth rate stagnates at about 8%. We used this information to plot the cumulative number of cases by date.

|May 11 update|
|:---:|
|![Projected cumulative cases][may11_total_chart]|



Since many parts of the country have been given relaxations after May 3rd, we are interested to know what to expect in the coming weeks. If the containment strategy proves to be successful, the curve will continue the same way till May 15 and then we can assume it will continue so till May 25. On the other hand, with the increased mobility if the infection rate starts to rise, the ground data will slowly start ramping up from May 13th and training the Neural Network with the new rates, we can predict how the cases would rise. With the change in social behaviour of the people who are letting down their guard, it is our opinion that the later is more likely to happen. So please check back for updates as we rerun the predictions in a few days.

[incubation]: https://annals.org/aim/fullarticle/2762808/incubation-period-coronavirus-disease-2019-covid-19-from-publicly-reported
[notebook]: https://github.com/VICS-CORE/stats/blob/master/01_Basic_predictions.ipynb
[daily_chart]: {{ site.baseurl }}/assets/images/gr/daily_cases.png
[nn_chart]: {{ site.baseurl }}/assets/images/gr/nn.png
[total_chart]: {{ site.baseurl }}/assets/images/gr/total_cases.png
[may11_total_chart]: {{ site.baseurl }}/assets/images/gr/total_cases_may11.png
[may11_nn_chart]: {{ site.baseurl }}/assets/images/gr/nn_may11.png
