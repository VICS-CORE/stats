---
layout: post
title: 10 day forecast using Deep Learning
date:   2020-06-04
comments: true
hero: /assets/images/forecasting/hero.jpeg
excerpt: Most researchers are using a compartmentalised model such as SIR or one of its variants to predict the Covid19 future, because the epidemiologists use them to describe epidemic growth. These work well when there is unhindered growth of the disease and when there is a uniform policy and pattern in the population under study. We felt that it was too much of a simplification to a heterogenous population like India where the policy and implementations are changing across states and with time.

---

| Date | Predicted daily cases | Actual daily cases | Difference |
|:---:|:---:|:---:|:---:|
| Jun 5  | 8818  | 9851 | 1033 |
| Jun 6  | 9373  | 9887 | 514 |
| Jun 7  | 9532  | 9971 | 439 |
| Jun 8  | 9706  | 9983 | 277 |
| Jun 9  | 9605  | 9987 | 382 |
| Jun 10 | 9896  | 9985 | 89 |
| Jun 11 | 10154 | 9996 | -158 |
| Jun 12 | 10091 | 10956 | 865 |
| Jun 13 | 9599  |  |  |
| Jun 14 | 9650  |  |  |

Predictions last updated: 4 Jun

Most researchers are using a compartmentalised model such as [SIR][sir_wiki]{:target="_blank"} or one of its variants to predict the Covid19 future, because the epidemiologists use them to describe epidemic growth. These work well when there is unhindered growth of the disease and when there is a uniform policy and pattern in the population under study. It worked well with small populations in European countries. We felt that it was too much of a simplification to a heterogenous population like India where the policy and implementations are changing across states and with time. Our case was more along the lines of the US where these models have proved to be inadequate. Further the number of people infected in India was too low and data too little to reliably use such models in the early stages when we started this work. Luckily we have deep neural networks which are generalized AI learning algorithms that can learn directly from the data and build a model on its own. We are using this to understand the pattern of confirmed cases across the world.

We built a model using Recurrent Neural Network (RNN) to predict the Covid19 confirmed cases for the next 10 days. RNNs can learn patterns from training data and make predictions accordingly. We trained the RNN on Covid [data][owid]{:target="_blank"} from all other countries of the world and asked it to make predictions for India.

Last updated: 4 Jun
![Predictions][chart]


Rudimentary algorithm fitting was to do a time series prediction using RNN which a few researchers attempted. But that approach was not rich enough as we needed a way to look at more inputs that might matter across multiple populations. We discovered a [paper by NYudistira][yud]{:target="_blank"} and agreed with his overall approach but disagreed on certain assumptions that were made. We made some improvements that are listed in our notebook [here][notebook]{:target="_blank"}.

Training these models is a computationally intensive task and requires GPUs. Our home computers proved insufficient to crunch the numbers and we took the help of Google Colab platform to run our programs. Currently it takes us over 48 hours to train one model and the platform access is unreliable. We're looking for sponsorship in terms of computational resources in order to crunch more numbers and provide better models and keep updating them as the pandemic progresses. If you like our direction and are able to help please do get in touch with us. Else please keep visiting us to see the updated forecast as we try to look at more inputs and outputs and extend the look ahead duration.

[chart]: {{ site.baseurl }}/assets/images/forecasting/chart.png
[sir_wiki]: https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model
[yud]: https://arxiv.org/abs/2005.04809
[notebook]: https://nbviewer.jupyter.org/github/VICS-CORE/stats/blob/master/11_YudistirNet.ipynb
[owid]: https://github.com/owid/covid-19-data/tree/master/public/data
