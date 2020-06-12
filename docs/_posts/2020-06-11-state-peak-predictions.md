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
Andaman & Nicobar Islands | Oct 01 | 69 | 3545
Andhra Pradesh | Sep 20 | 14311 | 697062
Arunachal Pradesh | Nov 08 | 3558 | 228398
Asaam | Aug 09 | 4998 | 272570
Bihar | Oct 01 | 14604 | 821905
Chandigarh | Dec 27 | 53 | 2338
Chhattisgarh | Sep 09 | 3625 | 179202
Delhi | Jun 24 | 2488 | 141890
Dadra & Nagar Haveli and Daman & Diu | Nov 24 | 106 | 4297
Goa | Jun 19 | 70 | 4748
Gujarat | Aug 29 | 9059 | 473340
Himachal Pradesh | Sep 27 | 766 | 58292
Haryana | Aug 04 | 4067 | 195165
Jharkhand | Aug 22 | 5037 | 232344
Jammu & Kashmir | Aug 09 | 2151 | 110561
Karnataka | Nov 18 | 14325 | 579448
Kerala | Oct 01 | 5124 | 236213
Ladakh | Dec 27 | 32 | 3460
Maharashtra | Jul 19 | 16796 | 1541915
Meghalaya | Oct 01 | 497 | 20659
Manipur | Aug 09 | 293 | 30338
Madhya Pradesh | Oct 21 | 8837 | 719312
Mizoram | Aug 02 | 100 | 7121
Nagaland | Oct 07 | 262 | 13674
Odisha | Oct 22 | 5719 | 417555
Punjab | Sep 20 | 5257 | 230506
Puducherry | Aug 22 | 233 | 10117
Rajasthan | Nov 24 | 9412 | 839299
Telangana | Oct 27 | 4731 | 336058
Tamil Nadu | Jul 17 | 11386 | 629946
Tripura | Dec 22 | 535 | 17910
Uttar Pradesh | Oct 01 | 27400 | 1798338
Uttarakhand | Dec 24 | 1065 | 29827
West Bengal | Aug 31 | 8665 | 558697

States in the order they peak, with peak daily cases listed as bars:
![Bar chart][bars]


The graphs for a few states were predicted incorrectly by our RNN because of insufficient data. The secondary wave has to be ignored for now till we refit the model with more training data.


[notebook]: https://nbviewer.jupyter.org/github/VICS-CORE/stats/blob/master/11_YudistirNet.ipynb
[training4020]: {{ site.baseurl }}/2020/06/04/20-day-forecaster.html

[10kstates]: {{ site.baseurl }}/assets/images/statesforecast/10kstates.png
[5kstates]: {{ site.baseurl }}/assets/images/statesforecast/5kstates.png
[2kstates]: {{ site.baseurl }}/assets/images/statesforecast/2kstates.png
[aggstates]: {{ site.baseurl }}/assets/images/statesforecast/aggstates.png
[bars]: {{ site.baseurl }}/assets/images/statesforecast/bars.png