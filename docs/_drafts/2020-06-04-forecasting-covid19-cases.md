---
layout: post
title: Forecasting Covid19 cases in India
date:   2020-06-04
comments: true
hero: /assets/images/forecasting/hero.jpeg

---

Mathematical models are used to explain and then predict the pattern of confirmed Covid19 cases. Typically, epidemiologists use [SIR][sir_wiki]{:target="_blank"} or one of its variants to describe epidemic growth. However practically it is not suited for heterogenous populations like India. Hence we used deep neural networks to understand the pattern of confirmed cases across the world.

We built a model using Recurrent Neural Network (RNN) to predict Covid19 confirmed cases for the next few days. RNNs can learn patterns from training data and make predictions accordingly. We trained the RNN on Covid [data][owid]{:target="_blank"} from all other countries of the world and asked it to make predictions for India.

Last updated: 4 Jun
![Predictions][chart]

| Date | Predicted daily cases | Actual daily cases | Error |
|:---:|:---:|:---:|:---:|
| Jun 5  | 8818  |  |  |
| Jun 6  | 9373  |  |  |
| Jun 7  | 9532  |  |  |
| Jun 8  | 9706  |  |  |
| Jun 9  | 9605  |  |  |
| Jun 10 | 9896  |  |  |
| Jun 11 | 10154 |  |  |
| Jun 12 | 10091 |  |  |
| Jun 13 | 9599  |  |  |
| Jun 14 | 9650  |  |  |

Our model is based on a [paper by NYudistira][yud]{:target="_blank"} but has some improvements and some limitations. For details, please check out the notebook [here][notebook]{:target="_blank"}. Our primary limitations are regarding computation time. Training these models is a compute intesive task and requires GPUs. Currently it takes us over 48 hours to train one model. We're looking for support in order to crunch more numbers and provide better models in the future.

[chart]: {{ site.baseurl }}/assets/images/forecasting/chart.png
[sir_wiki]: https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model
[yud]: https://arxiv.org/abs/2005.04809
[notebook]: https://github.com/VICS-CORE/stats/blob/master/11_YudistirNet.ipynb
[owid]: https://github.com/owid/covid-19-data/tree/master/public/data
