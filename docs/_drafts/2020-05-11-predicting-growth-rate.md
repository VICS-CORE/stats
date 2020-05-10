---
layout: post
title: Predicting growth rate of total infections
date:   2020-05-11
comments: true

---

Few days ago, we analysed the number of new cases per day and built a model to estimate the rate at which covid patients will grow in India. The following curve shows the number of new cases per day as of Apr 26th:

|Daily new cases as of Apr 26th|
|:---:|
|![New cases per day][daily_chart]|

According to [this report][incubation], most COVID19 patients take about 5 to 12 days to develop symptoms. This is known as _incubation period_. That implies, if a lockdown happens today, the number of cases will start reducing after at least 5 days. Similarly, if a lockdown ends today and number of people contacting each other increases, it'll take at least 5 days for the reported number of cases to increase.

Since lockdown in India started on Mar 24th, we chose to ignore the numbers till Apr 4th and trained the model using 21 days' data, i.e. Apr 5th to 26th. This would capture the behaviour of growth rate in a lockdown mode. So it should predict the growth accurately as long as the lockdown continues and 5-10 days thereafter.

In the following plot, the line in red denotes actual growth rate numbers from Apr 5th to 26th and the blue line denotes the projected numbers.

|Our model|
|:---:|
|![Our model][nn_chart]|

As it can be seen, the growth rate stagnates at about 7%. We used this information to plot the cumulative number of cases by date.

|Projected cumulative cases|
|:---:|
|![Projected cumulative cases][total_chart]|

According to this model, the cumulative number of infections rises to 50,000 after first week of May, which has held true. It predicts the number touching 1,00,000 around May 15th. 

Since many parts of the country have been given relaxations after May 3rd, we don't know what to expect in the coming weeks. But let's pray for the best.

[incubation]: https://annals.org/aim/fullarticle/2762808/incubation-period-coronavirus-disease-2019-covid-19-from-publicly-reported
[notebook]: https://github.com/VICS-CORE/stats/blob/master/01_Basic_predictions.ipynb
[daily_chart]: {{ site.baseurl }}/assets/images/gr/daily_cases.png
[nn_chart]: {{ site.baseurl }}/assets/images/gr/nn.png
[total_chart]: {{ site.baseurl }}/assets/images/gr/total_cases.png
