---
layout: post
title: Verification of Peak Death dates by University of Washington
date:   2020-05-08
comments: true
hero: /assets/images/uw/hero.jpg

---

A peak date is when the epidemic growth is at the maximum and after that the disease starts to subside. Hence it is of interest to know if a country or state has peaked. 

Scientists use a popular model called SIR to predict how epidemics such as Covid19 are spreading. The results of the prediction vary based on assumptions made to feed appropirate inputs to the model. Hence we found that there was a need to independently verify these predictions looking at the actual data recorded over time.

University of Washington through [it's website][hd_website]{:target="_blank"}, has been publishing its predicted Covid19 peak death dates for select American and European Countries. The death curve is calculated on the daily reported deaths and it should lag the curve of infections reported by reason. We were curious to verify these dates and built a methodology to validate these predictions.  We found that the average lag between the two curves is around 7 days. The choice of countries choosen for their study is disappointing and does not include many countries that have not yet peaked. We have discared some small countries which fall below our threshold to make the predictions more meaningful.

### Results

Last Updated: May 8, 2020. We plan to update these results every few days. So please check back for any changes.

Here is a comparison of peak dates as per University of Washington and our study.

<a name="table"></a>

Country | University of Washington | Our study (deaths) | Our study (new infections) | Lag in death and infections (days)
--- | --- | --- | --- | ---
[Austria](#austria)|Apr 08|Apr 10|Mar 28|13
[Belgium](#belgium)|Apr 10|Apr 14|Apr 12|2
[Czech Republic](#czech_republic)|Apr 14|Apr 11|Apr 02|9
[Denmark](#denmark)|Apr 04|Apr 07|Apr 07|0
[Estonia](#estonia)|Apr 02|Apr 06|Apr 04|2
[Finland](#finland)|Apr 21|Apr 24|Apr 09|15
[France](#france)|Apr 05|Apr 09|Apr 02|7
[Germany](#germany)|Apr 16|Apr 18|Apr 03|15
[Greece](#greece)|Apr 03|Apr 05|Apr 02|3
[Hungary](#hungary)|Apr 24|Apr 20|Apr 12|8
[Italy](#italy)|Mar 27|Mar 31|Mar 26|5
[Luxembourg](#luxembourg)|Apr 11|Apr 11|Mar 28|14
[Netherlands](#netherlands)|Apr 07|Apr 07|Apr 12|-5
[Norway](#norway)|Apr 20|Apr 13|Mar 29|15
[Portugal](#portugal)|Apr 03|Apr 14|Apr 04|10
[Slovenia](#slovenia)|Apr 07|Apr 10|Mar 30|11
[Spain](#spain)|Apr 01|Apr 03|Apr 01|2
[Switzerland](#switzerland)|Apr 04|Apr 07|Mar 30|8
[United Kingdom](#united_kingdom)|Apr 10|Apr 13|Apr 15|-2
[United States](#united_states)|Apr 15|Apr 18|Apr 10|8
[Canada](#canada)|Apr 16|not yet peaked|not yet peaked|-
[Croatia](#croatia)|Apr 19|not yet peaked|Mar 31|-

### Logic
The logic for this article has been mentioned in [our previous article][has_india_peaked].

### Graphs

Following is the list of charts for the countries mentioned above. For each country, there are two timeseries charts that have been plotted. First is the percentile epidemic curve, i.e. percentile of frequency of new patients per day. Second denotes the first order derivative of the epidemic curve, i.e. the change in daily cases. It is useful for finding peaks, which are marked by the vertical lines in the charts. Red lines indicate death cases plotted against time and blue lines indicate number of new infections reported, plotted against time. Similarly, a red vertical line is a death peak and a blue vertical line is a peak in the number of new infections reported.

| |
|:---:|
| <a name="austria"></a><br /> ![Austria][au_chart] <br />[Back](#table) |
| <a name="belgium"></a><br /> ![Belgium][be_chart] <br />[Back](#table) |
| <a name="czech_republic"></a><br /> ![Czech Republic][cz_chart] <br />[Back](#table) |
| <a name="denmark"></a><br /> ![Denmark][de_chart] <br />[Back](#table) |
| <a name="estonia"></a><br /> ![Estonia][es_chart] <br />[Back](#table) |
| <a name="finland"></a><br /> ![Finland][fi_chart] <br />[Back](#table) |
| <a name="france"></a><br /> ![France][fr_chart] <br />[Back](#table) |
| <a name="germany"></a><br /> ![Germany][ge_chart] <br />[Back](#table) |
| <a name="greece"></a><br /> ![Greece][gr_chart] <br />[Back](#table) |
| <a name="hungary"></a><br /> ![Hungary][hu_chart] <br />[Back](#table) |
| <a name="italy"></a><br /> ![Italy][it_chart] <br />[Back](#table) |
| <a name="luxembourg"></a><br /> ![Luxembourg][lu_chart] <br />[Back](#table) |
| <a name="netherlands"></a><br /> ![Netherlands][ne_chart] <br />[Back](#table) |
| <a name="norway"></a><br /> ![Norway][no_chart] <br />[Back](#table) |
| <a name="portugal"></a><br /> ![Portugal][po_chart] <br />[Back](#table) |
| <a name="slovenia"></a><br /> ![Slovenia][sl_chart] <br />[Back](#table) |
| <a name="spain"></a><br /> ![Spain][sp_chart] <br />[Back](#table) |
| <a name="switzerland"></a><br /> ![Switzerland][sw_chart] <br />[Back](#table) |
| <a name="united_kingdom"></a><br /> ![United Kingdom][uk_chart] <br />[Back](#table) |
| <a name="united_states"></a><br /> ![United States][us_chart] <br />[Back](#table) |
| <a name="canada"></a><br /> ![Canada][ca_chart] <br />[Back](#table) |
| <a name="croatia"></a><br /> ![Croatia][cr_chart] <br />[Back](#table) |

[hd_website]: https://covid19.healthdata.org/projections
[has_india_peaked]: {{ site.baseurl }}/2020/04/30/has-india-peaked-yet.html

[au_chart]: {{ site.baseurl }}/assets/images/uw/austria.png
[be_chart]: {{ site.baseurl }}/assets/images/uw/belgium.png
[cz_chart]: {{ site.baseurl }}/assets/images/uw/czech_republic.png
[de_chart]: {{ site.baseurl }}/assets/images/uw/denmark.png
[es_chart]: {{ site.baseurl }}/assets/images/uw/estonia.png
[fi_chart]: {{ site.baseurl }}/assets/images/uw/finland.png
[fr_chart]: {{ site.baseurl }}/assets/images/uw/france.png
[ge_chart]: {{ site.baseurl }}/assets/images/uw/germany.png
[gr_chart]: {{ site.baseurl }}/assets/images/uw/greece.png
[hu_chart]: {{ site.baseurl }}/assets/images/uw/hungary.png
[it_chart]: {{ site.baseurl }}/assets/images/uw/italy.png
[lu_chart]: {{ site.baseurl }}/assets/images/uw/luxembourg.png
[ne_chart]: {{ site.baseurl }}/assets/images/uw/netherlands.png
[no_chart]: {{ site.baseurl }}/assets/images/uw/norway.png
[po_chart]: {{ site.baseurl }}/assets/images/uw/portugal.png
[sl_chart]: {{ site.baseurl }}/assets/images/uw/slovenia.png
[sp_chart]: {{ site.baseurl }}/assets/images/uw/spain.png
[sw_chart]: {{ site.baseurl }}/assets/images/uw/switzerland.png
[uk_chart]: {{ site.baseurl }}/assets/images/uw/united_kingdom.png
[us_chart]: {{ site.baseurl }}/assets/images/uw/united_states.png
[ca_chart]: {{ site.baseurl }}/assets/images/uw/canada.png
[cr_chart]: {{ site.baseurl }}/assets/images/uw/croatia.png
