---
layout: post
title: Can you guess which state will end up having the most Covid-19 cases?
date:   2020-06-11
comments: true
hero: /assets/images/states/hero.png

---

Currently we are seeing that Mumbai, Delhi, Chennai and Ahmedabad together account for 2/3d of the cases. But the same trend would not continue for long. When all of this is over, UP would end up being the state that would report the maximum number of daily cases.

A peak date is when the epidemic growth is at the maximum and after that the disease starts to subside. Hence it is of interest to know if a country or state has peaked. In our previous post [4020model], we described how we trained a 20 day forecaster using Deep learning and a Recurring Neural Network. Feeding back the predicted data as actual data in a recursive loop we can extend the prediction even further. We did exactly this and extended the forecast till ... We found that these 7 states would end up reporting more than 10K cases daily. 


Then these 7 states would report more than 5K cases daily.


Here are the remaining states

Now summing up these state level graphs, we calculate the aggregate graph for India which looks like this.

Peak Date: 
Peak Daily new cases:
Cummulative Confirmed cases:



Our calculations and code is available in this [notebook][notebook]{:target="_blank"}.


### Results

Last Updated: June 11, 2020. We plan to update these results every few days. So please check back for any changes.

<a name="table"></a>
The following table shows a list of states in the order they peak

State | Peak date | Peak daily cases| Cummulative cases
 --- | ---
[Andhra Pradesh](#ap)|Apr 29
[Assam](#as)|Apr 04
[Bihar](#bi)|Apr 28
[Chandigarh](#ch)|May 04
[Jharkhand](#jh)|Apr 27
[Karnataka](#kt)|Apr 18
[Kerala](#kl)|Mar 29
[Madhya Pradesh](#mp)|Apr 28
[Telangana](#tg)|Apr 06
[Uttarakhand](#uk)|Apr 06

<a name="table2"></a>
The following table shows a list of states by the number of cases that they will end up having

State | Peak date | Peak daily cases| Cummulative cases
 --- | ---
| [Chhattisgarh](#cg) |
| [Delhi](#dl) |
| [Gujarat](#gj) |
| [Harayana](#hr) |
| [Jammu & Kashmir](#jk) |
| [Maharashtra*](#mh) |
| [Mumbai*](#mu) |
| [Odisha](#od) |
| [Punjab](#pb) |
| [Rajasthan](#rj)|
| [Tamil Nadu](#tn) |
| [Tripura](#tp) |
| [Uttar Pradesh](#up) |
| [West Bengal](#wb) |


BarChart - States in the order they peak listed as bars with their peak values as the dimension.


### Graphs

Following is the list of charts for all the states mentioned above where the peak cases is greater than 100. 
| |
|:---:|
| <a name="ap"></a><br /> ![Andhra Pradesh][ap_chart] <br />[Back](#table) |
| <a name="as"></a><br /> ![Assam][as_chart] <br />[Back](#table) |
| <a name="bi"></a><br /> ![Bihar][bi_chart] <br />[Back](#table) |
| <a name="ch"></a><br /> ![Chandigarh][ch_chart] <br />[Back](#table) |
| <a name="jh"></a><br /> ![Jharkhand][jh_chart] <br />[Back](#table) |
| <a name="kt"></a><br /> ![Karnataka][kt_chart] <br />[Back](#table) |
| <a name="kl"></a><br /> ![Kerala][kl_chart] <br />[Back](#table) |
| <a name="mp"></a><br /> ![Madhya Pradesh][mp_chart] <br />[Back](#table) |
| <a name="tg"></a><br /> ![Telangana][tg_chart] <br />[Back](#table) |
| <a name="uk"></a><br /> ![Uttarakhand][uk_chart] <br />[Back](#table) |
| <a name="cg"></a><br /> ![Chhattisgarh][cg_chart] <br />[Back](#table2) |
| <a name="dl"></a><br /> ![Delhi][dl_chart] <br />[Back](#table2) |
| <a name="gj"></a><br /> ![Gujarat][gj_chart] <br />[Back](#table2) |
| <a name="hr"></a><br /> ![Harayana][hr_chart] <br />[Back](#table2) |
| <a name="jk"></a><br /> ![Jammu & Kashmir][jk_chart] <br />[Back](#table2) |
| <a name="mh"></a><br /> ![Maharashtra*][mh_chart] <br />[Back](#table2) |
| <a name="mu"></a><br /> ![Mumbai*][mu_chart] <br />[Back](#table2) |
| <a name="od"></a><br /> ![Odisha][od_chart] <br />[Back](#table2) |
| <a name="pb"></a><br /> ![Punjab][pb_chart] <br />[Back](#table2) |
| <a name="rj"></a><br /> ![Rajasthan][rj_chart] <br />[Back](#table2) |
| <a name="tn"></a><br /> ![Tamil Nadu][tn_chart] <br />[Back](#table2) |
| <a name="tp"></a><br /> ![Tripura][tp_chart] <br />[Back](#table2) |
| <a name="up"></a><br /> ![Uttar Pradesh][up_chart] <br />[Back](#table2) |
| <a name="wb"></a><br /> ![West Bengal][wb_chart] <br />[Back](#table2) |


The graphs for the following states were wrongly predicted by our RNN and the secondary wave has to be ignored for now till we refit the model with more training data.


[notebook]: https://github.com/VICS-CORE/stats/blob/master/02_Peak_calculator.ipynb
[hasindiapeaked]: {{ site.baseurl }}/2020/04/30/has-india-peaked-yet.html

[ap_chart]: {{ site.baseurl }}/assets/images/states/andhra_pradesh.png
[as_chart]: {{ site.baseurl }}/assets/images/states/assam.png
[bi_chart]: {{ site.baseurl }}/assets/images/states/bihar.png
[ch_chart]: {{ site.baseurl }}/assets/images/states/chandigarh.png
[cg_chart]: {{ site.baseurl }}/assets/images/states/chhattisgarh.png
[dl_chart]: {{ site.baseurl }}/assets/images/states/delhi.png
[gj_chart]: {{ site.baseurl }}/assets/images/states/gujarat.png
[hr_chart]: {{ site.baseurl }}/assets/images/states/haryana.png
[jk_chart]: {{ site.baseurl }}/assets/images/states/jammu_and_kashmir.png
[jh_chart]: {{ site.baseurl }}/assets/images/states/jharkhand.png
[kt_chart]: {{ site.baseurl }}/assets/images/states/karnataka.png
[kl_chart]: {{ site.baseurl }}/assets/images/states/kerala.png
[mp_chart]: {{ site.baseurl }}/assets/images/states/madhya_pradesh.png
[mh_chart]: {{ site.baseurl }}/assets/images/states/maharashtra.png
[mu_chart]: {{ site.baseurl }}/assets/images/states/mumbai.png
[od_chart]: {{ site.baseurl }}/assets/images/states/odisha.png
[pb_chart]: {{ site.baseurl }}/assets/images/states/punjab.png
[rj_chart]: {{ site.baseurl }}/assets/images/states/rajasthan.png
[tn_chart]: {{ site.baseurl }}/assets/images/states/tamil_nadu.png
[tg_chart]: {{ site.baseurl }}/assets/images/states/telangana.png
[tp_chart]: {{ site.baseurl }}/assets/images/states/tripura.png
[uk_chart]: {{ site.baseurl }}/assets/images/states/uttarakhand.png
[up_chart]: {{ site.baseurl }}/assets/images/states/uttar_pradesh.png
[wb_chart]: {{ site.baseurl }}/assets/images/states/west_bengal.png