---
layout: post
title: Can you guess which state will end up having the most Covid-19 cases?
date:   2020-06-11
comments: true
hero: /assets/images/statesforecast/hero.jpg

---

Currently we are seeing that Mumbai, Delhi, Chennai and Ahmedabad together account for 2/3rd of the cases. But the same trend would not continue for long. When all of this is over, UP would end up being the state that would report the maximum number of daily cases.

A peak date is when the epidemic growth is at the maximum and after that the disease starts to subside. Hence it is of interest to know if a country or state has peaked. In our [previous post][training4020], we described how we trained a 20 day forecaster using deep learning and a Recurrent Neural Network. Feeding back the predicted data as input data in a recursive loop, we can extend the prediction even further. We did exactly this and extended the forecast for next 6 months. We found that the following states would end up reporting more than 10K cases daily: 

![10k states][10kstates]

Then these states would report more than 5K cases daily:

![5k states][5kstates]

Lastly, these states would report more than 2K cases every day:

![2k states][2kstates]

Now summing up all the state level graphs, we calculate the aggregate graph for India which looks like this:

![agg states][aggstates]

Peak date: Oct 6, 2020

Peak daily new cases: 93,414

Cumulative confirmed cases: 1,14,46,050

A more textured graph can be drawn once we have district wise granular data.

Our calculations and code is available in this [notebook][notebook]{:target="_blank"}.

### Results
Last Updated: June 11, 2020. 

We plan to update these results every few days. So please check back for any changes.

<a name="table"></a>
The following table shows a list of states along with their peak dates, peak daily cases and cumulative cases.

State | Peak date | Peak daily cases| Cumulative cases
 --- | ---
Andaman & Nicobar Islands | Oct 01 | 69 | 3,545
Andhra Pradesh | Sep 20 | 14,311 | 6,97,062
Arunachal Pradesh | Nov 08 | 3,558 | 2,28,398
Asaam | Aug 09 | 4,998 | 2,72,570
Bihar | Oct 01 | 14,604 | 8,21,905
Chandigarh | Dec 27 | 53 | 2,338
Chhattisgarh | Sep 09 | 3,625 | 1,79,202
Delhi | Jun 24 | 2,488 | 1,41,890
Dadra & Nagar Haveli and Daman & Diu | Nov 24 | 106 | 4,297
Goa | Jun 19 | 70 | 4,748
Gujarat | Aug 29 | 9,059 | 4,73,340
Himachal Pradesh | Sep 27 | 766 | 58,292
Haryana | Aug 04 | 4,067 | 1,95,165
Jharkhand | Aug 22 | 5,037 | 2,32,344
Jammu & Kashmir | Aug 09 | 2,151 | 1,10,561
Karnataka | Nov 18 | 14,325 | 5,79,448
Kerala | Oct 01 | 5,124 | 2,36,213
Ladakh | Dec 27 | 32 | 3,460
Maharashtra | Jul 19 | 16,796 | 15,41,915
Meghalaya | Oct 01 | 497 | 20,659
Manipur | Aug 09 | 293 | 30,338
Madhya Pradesh | Oct 21 | 8,837 | 7,19,312
Mizoram | Aug 02 | 100 | 7,121
Nagaland | Oct 07 | 262 | 13,674
Odisha | Oct 22 | 5,719 | 4,17,555
Punjab | Sep 20 | 5,257 | 2,30,506
Puducherry | Aug 22 | 233 | 10,117
Rajasthan | Nov 24 | 9,412 | 8,39,299
Telangana | Oct 27 | 4,731 | 3,36,058
Tamil Nadu | Jul 17 | 11,386 | 6,29,946
Tripura | Dec 22 | 535 | 17,910
Uttar Pradesh | Oct 01 | 27,400 | 17,98,338
Uttarakhand | Dec 24 | 1,065 | 29,827
West Bengal | Aug 31 | 8,665 | 5,58,697

States in the order they peak, with peak daily cases listed as bars:
![Bar chart][bars]


The graphs for a few states were predicted incorrectly by our RNN because of insufficient data. The secondary wave has to be ignored for now till we refit the model with more training data.


[notebook]: https://nbviewer.jupyter.org/github/VICS-CORE/stats/blob/master/11_YudistirNet.ipynb
[training4020]: {{ site.baseurl }}/2020/06/04/20-day-forecaster.html

[10kstates]: {{ site.baseurl }}/assets/images/statesforecast/10kstates.png
[5kstates]: {{ site.baseurl }}/assets/images/statesforecast/5kstates.png
[2kstates]: {{ site.baseurl }}/assets/images/statesforecast/2kstates.png
[aggstates]: {{ site.baseurl }}/assets/images/statesforecast/aggstates.png
[bars]: {{ site.baseurl }}/assets/images/statesforecast/bars2.png