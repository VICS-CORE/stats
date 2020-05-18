---
layout: post
title: Has any state in India won over Corona yet?
date:   2020-05-07
comments: true
hero: /assets/images/states/hero.png

---
This is a question that every curious Indian wants to know. Apart from the political claims which we consider to be just noise, is there a scientific way to actually confirm this?  

A peak date is when the epidemic growth is at the maximum and after that the disease starts to subside. Hence it is of interest to know if a country or state has peaked. Scientists use a popular model called SIR to predict how epidemics such as Covid19 are spreading. The simple SIR model has a few variants all which work well for a small homogeneous populations. India is a vast country and the dynamics of the disease spread in the country can not be acurately predicted by a simple SIR model. The daily graph is a superimposition of many curves that describe the dynamics of its various parts that make up India. The states, metros and bigger cities have their own dynamics and each have to be modelled seperately. We have started working on the mathematics to develop a generalized wave model to take care of the aggregate dynamics of a complex country such as India. Though we don't have a prediction model ready yet, we have developed a methodology to verify the peaks by examining the actual data. 

Our method has a limitation that it can confirm the peak only 3 days after the actual peak date. After running our calculations, we found that it seems like some of the states have peaked. However it is too early to say this with confidence as secondary waves can be started as the movement of people starts between places. If the containment does succeed then we can consider that some of the states have peaked. We have considered Mumbai district as a run away case which interferes with the actual analysis of the disease for Maharastra or even the whole nation. The peaks predicted are tentative and will be rendered as a false positives if and when a new peak is formed. This iterative process will continue till a sizeable portion of the population under consideration gets infected. Since the administration has enforced severe lockdown measures, a free run for the epidemic as per the SIR model will not happen and we are much early in the growth state. The logic for our analysis was presented in [our earlier article][hasindiapeaked] and our calculations and code is available in this [notebook][notebook]{:target="_blank"}.


### Results

Last Updated: May 7, 2020. We plan to update these results every few days. So please check back for any changes.

<a name="table"></a>
The following table shows a list of states which seem to have hit the peak tentatively:

State | Peak date
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
This table shows states that have not yet peaked:

| State |
| --- |
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

*Mumbai has been considered separate from Maharashtra for drawing a clearer picture.

### Graphs

Following is the list of charts for the states mentioned above. For each states, there are two timeseries charts that have been plotted. The first is the percentile epidemic curve, i.e. percentile of frequency of new patients per day. The second denotes the first order derivative of the epidemic curve, i.e. the change in daily cases. It is useful for finding peaks, which are marked by the vertical blue lines in the charts.

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