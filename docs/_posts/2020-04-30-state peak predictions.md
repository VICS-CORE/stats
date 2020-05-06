---
layout: post
title: Has any state in India won over Corona yet?
date:   2020-04-30

---
This is a question that curious Indian wants to know. Though we don't have a prediction model we developed a methodology to verify the peaks by looking at the actual data. India is a vast country and the dynamics of the country can not be easily modelled by the simple SIR model which worked well for most smaller countries. The daily graph is a superimposition of many curves that describe the dynamics of its various parts that make up India. The states, metros and bigger cities have their own dynamics and have to be modelled with an enhanced SIR model or one of it's variants. 

Our method has a limitation that it can confirm the peak only 3 days after the actual peak date. After running our calculations, we found that it seems like some of the states have peaked. However it is true early to say this as secondary waves can be started as the movement of people starts between places. If the containment does succeed then we can consider that some of the states have peaked. We have considered Mumbai district as a run away case which interefers with the actual growth of the disease for Maharastra or even the whole nation. The peaks are tentative and will be rendered a false positive when a new peak is formed.  This iterative process will continue till a sizeable portion of the population gets infected. Since the administration has enforced severe lockdown measures, a free run for the epidemic as per the SIR model will not happen and we are much early in the growth state. The details of our analysis are presented [here][paper] and our calculations and code is available in this [notebook][notebook]{:target="_blank"}. 


### Results

Last Updated: May 5, 2020. We plan to update these results every few days. So please checkback for any changes.

![India][in_chart]

<a name="table"></a>
The following table shows a list of states which seem to have hit the peak yet:

Country | SUTD | Our verification
 --- | --- | ---
[Afghanistan](#Afghanistan)|Apr 29|not peaked
[Bangladesh](#Bangladesh)|Apr 23|not peaked
[Brazil](#Brazil)|Apr 21|not peaked
[Chile](#Chile)|Apr 16|not peaked
[India](#India)|Apr 20|not peaked
[Indonesia](#Indonesia)|Apr 20|not peaked
[Mexico](#Mexico)|May 01|not peaked
[Pakistan](#Pakistan)|Apr 27|not peaked
[Peru](#Peru)|Apr 18|not peaked
[Russia](#Russia)|Apr 24|not peaked
[Saudi Arabia](#SA)|Apr 27|not peaked
[United Arab Emirates](#UAE)|Apr 17|not peaked

<a name="table2"></a>
This table shows states that have not yet peaked
Country | SUTD | Our verification
 --- | --- | ---
[Australia](#Australia)|Mar 27|Mar 28
[Austria](#Austria)|Mar 26|Mar 28
[China](#China)|Feb 08|Feb 13
[Denmark](#Denmark)|Apr 06|Apr 07
[Finland](#Finland)|Apr 11|Apr 09
[France](#France)|Apr 03|Apr 02
[Germany](#Germany)|Apr 01|Apr 03
[Greece](#Greece)|Mar 30|Apr 02
[Hungary](#Hungary)|Apr 15|Apr 12
[Iran](#Iran)|Apr 01|Apr 02
[Iraq](#Iraq)|Apr 04|Apr 08
[Israel](#Israel)|Apr 04|Apr 04
[Italy](#Italy)|Mar 29|Mar 26
[Malaysia](#Malaysia)|Mar 31|Apr 04
[Netherlands](#Netherlands)|Apr 08|Apr 12
[Norway](#Norway)|Mar 27|Mar 29
[Philippines](#Philippines)|Apr 07|Apr 03
[Portugal](#Portugal)|Apr 06|Apr 04
[South Korea](#SK)|Mar 02|Mar 03
[Spain](#Spain)|Apr 02|Apr 01
[Sweden](#Sweden)|Apr 20|Apr 25
[Switzerland](#Switzerland)|Mar 29|Mar 30
[Thailand](#Thailand)|Mar 28|Apr 01
[United Kingdom](#UK)|Apr 12|Apr 15
[United States](#US)|Apr 10|Apr 10

### Logic

We use basic calculus to identify the peak. A peak on the daily epidemic curve (i.e. new patients per day) is a maximum. To identify maxima and minima on a curve, we use the fact that first order derivative becomes zero at that point. So we calculate change in daily cases which denotes the `slope` of the curve and identify dates where this curve becomes 0. Each point is a potential peak. 

However, we find multiple such points since the derivative becomes 0 whenever the curve is parallel to x-axis. To further verify that it is a true peak, we cross examine the second order derivative. At maximums, the second derivative, i.e. `change in slope`, should be negative because the slope changes from positive to negative at a peak.

![Derivative Diagram][derivative]


### Graphs

Following is the list of charts for the states mentioned above. For each states, there are two timeseries charts that have been plotted. First is the percentile epidemic curve, i.e. percentile of frequency of new patients per day. Second denotes the first order derivative of the epidemic curve, i.e. the change in daily cases. It is useful for finding peaks, which are marked by the vertical blue lines in the charts.

| |
|:---:|
| <a name="India"></a><br /> ![India][in_chart] <br />[Back](#table)|
| <a name="UAE"></a><br /> ![United Arab Emirates][ae_chart] <br />[Back](#table) |
| <a name="Russia"></a><br /> ![Russia][ru_chart] <br />[Back](#table) |
| <a name="Peru"></a><br /> ![Peru][pe_chart] <br />[Back](#table) |
| <a name="Mexico"></a><br /> ![Mexico][mx_chart] <br />[Back](#table) |
| <a name="Pakistan"></a><br /> ![Pakistan][pk_chart] <br />[Back](#table) |
| <a name="Bangladesh"></a><br /> ![Bangladesh][bd_chart] <br />[Back](#table) |
| <a name="Chile"></a><br /> ![Chile][cl_chart] <br />[Back](#table) |
| <a name="SA"></a><br /> ![Saudi Arabia][sa_chart] <br />[Back](#table) |
| <a name="Brazil"></a><br /> ![Brazil][br_chart] <br />[Back](#table) |
| <a name="Afghanistan"></a><br /> ![Afghanistan][af_chart] <br />[Back](#table) |
| <a name="Indonesia"></a><br /> ![Indonesia][id_chart] <br />[Back](#table) |
| <a name="China"></a><br /> ![China][cn_chart] <br />[Back](#table2) |
| <a name="SK"></a><br /> ![South Korea][sk_chart] <br />[Back](#table2) |
| <a name="US"></a><br /> ![United States][us_chart] <br />[Back](#table2) |
| <a name="UK"></a><br /> ![United Kingdom][uk_chart] <br />[Back](#table2) |
| <a name="Italy"></a><br /> ![Italy][it_chart] <br />[Back](#table2) |
| <a name="Spain"></a><br /> ![Spain][es_chart] <br />[Back](#table2) |
| <a name="Germany"></a><br /> ![Germany][de_chart] <br />[Back](#table2) |
| <a name="France"></a><br /> ![France][fr_chart] <br />[Back](#table2) |
| <a name="Portugal"></a><br /> ![Portugal][pt_chart] <br />[Back](#table2) |
| <a name="Australia"></a><br /> ![Australia][au_chart] <br />[Back](#table2) |
| <a name="Austria"></a><br /> ![Austria][at_chart] <br />[Back](#table2) |
| <a name="Denmark"></a><br /> ![Denmark][dk_chart] <br />[Back](#table2) |
| <a name="Finland"></a><br /> ![Finland][fi_chart] <br />[Back](#table2) |
| <a name="Greece"></a><br /> ![Greece][gr_chart] <br />[Back](#table2) |
| <a name="Hungary"></a><br /> ![Hungary][hu_chart] <br />[Back](#table2) |
| <a name="Iran"></a><br /> ![Iran][ir_chart] <br />[Back](#table2) |
| <a name="Iraq"></a><br /> ![Iraq][iq_chart] <br />[Back](#table2) |
| <a name="Israel"></a><br /> ![Israel][il_chart] <br />[Back](#table2) |
| <a name="Malaysia"></a><br /> ![Malaysia][my_chart] <br />[Back](#table2) |
| <a name="Netherlands"></a><br /> ![Netherlands][nl_chart] <br />[Back](#table2) |
| <a name="Norway"></a><br /> ![Norway][no_chart] <br />[Back](#table2) |
| <a name="Philippines"></a><br /> ![Philippines][ph_chart] <br />[Back](#table2) |
| <a name="Sweden"></a><br /> ![Sweden][se_chart] <br />[Back](#table2) |
| <a name="Switzerland"></a><br /> ![Switzerland][ch_chart] <br />[Back](#table2) |
| <a name="Thailand"></a><br /> ![Thailand][th_chart] <br />[Back](#table2) |

[sutd_paper]: https://www.altaveu.com/documents/covid19predictionpaper20200426.pdf
[sutd_website]: https://ddi.sutd.edu.sg/when-will-covid-19-end/
[notebook]: https://github.com/VICS-CORE/stats/blob/master/02_Total_daily_slope.ipynb
[paper]: {{ site.baseurl }}/papers/cpec

[in_chart]: {{ site.baseurl }}/assets/images/02/india.png
[ae_chart]: {{ site.baseurl }}/assets/images/02/united_arab_emirates.png
[ru_chart]: {{ site.baseurl }}/assets/images/02/russia.png
[pe_chart]: {{ site.baseurl }}/assets/images/02/peru.png
[mx_chart]: {{ site.baseurl }}/assets/images/02/mexico.png
[pk_chart]: {{ site.baseurl }}/assets/images/02/pakistan.png
[bd_chart]: {{ site.baseurl }}/assets/images/02/bangladesh.png
[cl_chart]: {{ site.baseurl }}/assets/images/02/chile.png
[sa_chart]: {{ site.baseurl }}/assets/images/02/saudi_arabia.png
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
[af_chart]: {{ site.baseurl }}/assets/images/02/afghanistan.png
[au_chart]: {{ site.baseurl }}/assets/images/02/australia.png
[at_chart]: {{ site.baseurl }}/assets/images/02/austria.png
[dk_chart]: {{ site.baseurl }}/assets/images/02/denmark.png
[fi_chart]: {{ site.baseurl }}/assets/images/02/finland.png
[gr_chart]: {{ site.baseurl }}/assets/images/02/greece.png
[hu_chart]: {{ site.baseurl }}/assets/images/02/hungary.png
[id_chart]: {{ site.baseurl }}/assets/images/02/indonesia.png
[ir_chart]: {{ site.baseurl }}/assets/images/02/iran.png
[iq_chart]: {{ site.baseurl }}/assets/images/02/iraq.png
[il_chart]: {{ site.baseurl }}/assets/images/02/israel.png
[my_chart]: {{ site.baseurl }}/assets/images/02/malaysia.png
[nl_chart]: {{ site.baseurl }}/assets/images/02/netherlands.png
[no_chart]: {{ site.baseurl }}/assets/images/02/norway.png
[ph_chart]: {{ site.baseurl }}/assets/images/02/philippines.png
[se_chart]: {{ site.baseurl }}/assets/images/02/sweden.png
[ch_chart]: {{ site.baseurl }}/assets/images/02/switzerland.png
[th_chart]: {{ site.baseurl }}/assets/images/02/thailand.png

[derivative]: {{ site.baseurl }}/assets/images/02/derivative.jpg