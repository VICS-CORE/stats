---
layout: post
title: Verification of the Peak Death dates by University of Washington
date:   2020-04-30

---

A peak date is when the epidemic growth is at the maximum and after that the disease starts to subside. Hence it is of interest to know if a country or state has peaked. Scientists use a popular model called SIR to predict how epidemics such as COVID-19 are spreading. The results of the prediction vary based on assumptions made to feed appropirate inputs to the model. Hence we found that there was a need to independently verify these predictions looking at the actual data recorded over time.

University of Washington through it's website healthdata[hd_website], has been publishing its predicted COVID-19 peak death dates for select American and European Countries. The death curve is calculated on the daily reported deaths and it should lag the curve of infections reported by reason. We were curious to verify these dates and built a methodology to validate these predictions.  We found that the average lag between the two curves is around 5 days. The choice of countries choosen for their study is disappointing and does not include many countries that have not yet peaked. We have discared some small countries who fall below our threshold to make the predictions more meaningful.

### Results

Last Updated: May 5, 2020. We plan to update these results every few days. So please checkback for any changes.

![India][in_chart]

Here is a comparison of peak dates as per University of Washington and our study.

#This table has to be the link preview in FB

<a name="table2"></a>
This table shows countries that have already hit the peak number of new infections in a day:

Country | SUTD | Our verification ¦ difference (in days)
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
The logic for this article has been mentioned in our previous article [hasindiapeaked]

### Graphs

Following is the list of charts for the countries mentioned above. For each country, there are two timeseries charts that have been plotted. First is the percentile epidemic curve, i.e. percentile of frequency of new patients per day. Second denotes the first order derivative of the epidemic curve, i.e. the change in daily cases. It is useful for finding peaks, which are marked by the vertical blue lines in the charts.

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