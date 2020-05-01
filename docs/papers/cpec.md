---
layout: page
permalink: /papers/cpec

---

## Confirming Peak of the Epidemic Curve (CPEC) for COVID-19 pandemic

\- Mayank Bhagya & Radhesh Mohandas

### Abstract


### Introduction

An epidemic curve shows the distribution of newly infected cases as a bell curve. A peak on that curve is the day when the highest number of individuals are found to be infected and post that the frequency is reduced. Predicting the peak is of significance since it indicates the maximum number of infected patients requiring care at the same time. It can help the administration to prepare the healthcare system and also estimate on when the epidemic might end. There are many models to predict the peak date and the most popular one for this case is SIR and its variants.

In this study, we have built up a methodology to confirm the peak dates predicted by any such model. 
Recently, Data Driven Innovation lab (DDI) at Singapore University of Technology and Design (SUTD) came out with an [implementation][sutd_paper] of the SIR model and tried to predict the Covid-19 peak dates for various countries. 

Similarly, Institute for Health Metrics and Evaluation (IHME) at University of Washington (UW) has come up with [models][uw_paper] which declare peaks for select American and European countries.

We'll verify whether the peak dates provided by these two models are correct or not.

### Methodology

### Conclusion

We find that the dates predicted by UW are correct and may have an offset of a day or two for the reasons stated above. The dates predicted by SUTD are also verified for the countries that have clearly passed the peak. But for the countries which are still in the rising half of the epidemic, the dates predicted are incorrect in most of the cases.

[sutd_paper]: https://www.altaveu.com/documents/covid19predictionpaper20200426.pdf
[uw_paper]: https://covid19.healthdata.org/
