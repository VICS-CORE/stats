---
layout: post
title: Insights into our prediction models
date:   2020-07-11
comments: true
hero: /assets/images/sevaml/faq.jpeg

---

We believe in socially responsible research. We are answering some questions related to our work so that the technical community can understand what we are doing and come up with ways to help.

#### Why is Covid-19 case prediction Important?
Prediction is important as it will help the administration to plan for necessary resources and in turn save lives. For eg. if the administration has a plane full of ventilators, they should be able to decide which place they have to send it to right now so that maximum lives can be saved. Individuals will also be able to plan their lives around the pandemic and hence a public and transparent communication of the results is the need of the hour which we are doing with  [sevaml]

#### Are you using SIR for your modelling?
Compartmentalized models like SIR and it’s variants were built for infectious diseases like common flu that progressed unchecked and reached certain limiting levels. They expected 60-80 percent of the population to get infected until a herd immunity is reached. What we are seeing in most European countries that are coming out of the pandemic, is that only 3 to 6 percent of their population will probably end up getting infected in the first wave. Hence they are failing to describe what is happening on the ground. Further there is confusion and disagreement among the researchers on assumptions and applying of the parameters. Hence two peers using the same model are predicting outcomes factors apart. This is because we don’t have the mathematics developed to accurately describe the effects of restrictions such as a lockdown or it’s intensity yet. Further these restrictions are continuously changing and social response is also varying across communities. These work well with homogenous populations such as small European countries but we need higher granularity to describe a heterogeneous populations such as India. We have already seen in the case of the US which is now again detecting record new cases after an initial prediction of a peak in April.

#### What is your approach to solve the problem?
Since Mathematical models had the problems mentioned above, we decided to just look at the data and ask AI machines to look for patterns and build models which allowed us to be agnostic of the underlying causes. We are using deep learning to build our models where we are feeding the data of as many as 160 countries to an AI machine. The machine looks at thousands of variables and creates different weights which it keeps adjusting and we think using such an universal approximator is the best way forward. Further the pandemic is becoming a classical case of ‘The Butterfly effect’ where small changes in the initial conditions are resulting in large effects in the way the disease spreads. So we are building progressive models where our algorithms learn and correct as the ground reality changes. The predictions are updated daily to capture the results of the Government actions such as a lockdown or a relaxation and the social response to these. 

#### What exactly are you using for your Deep Learning?
We are using a RNN (Recursive Neural Network) for making the predictions. We take true data from all the countries that have seen the pandemic for more than 90 days, (more than 160 as of now) and divide it into two buckets in the ratio 7:3. The first bucket is used to train the network and the second bucket is used to validate the results. If the error is converging during the training process then it means the network is learning. If the validation accuracy is good then we know that the network has learnt well. Once we evaluate the accuracy of these two steps as good, the model is in essence an universal approximator.  Now the data for India is the test data which is never shown to the network during the training and validation phase. If the back test of the predictions for India is above certain accuracy, then we consider further evaluation of the model.

#### Where are you sourcing your data from?
We are currently finding daily updates from [owid] and [covid] sites. We are in the process of adding more data from more sites if we get reliable and open data. The accuracy of our results depends on the quality of the data and with the granularity that we need across all the countries of the world. Finding such sources is always a challenge.

#### What are the inputs and outputs to your model?
Initially we built an univariate model where the daily confirmed cases was the only variable dealt with. But now we are considering CARD (Confirmed, Active, Recovered and Death) and are building multivariate models where we can add many correlated variables as inputs. There is a single output for the multivariate model and we have to build a multitasking model to get all the relevant outputs.

#### What is your technical set up?
We are running python code in Jupyter notebooks. Our code is open source and hosted on GitHub. We are using PyTorch API for the RNN and Neptune as our experiment management system. We are using Google Cloud for computation. The web App is modified from the [covid] code base which is built on React Framework. Our blog is hosted on GitHub Pages using Jekyll.

#### Why don’t you try time series prediction?
Time series prediction works well with cyclical variables. For eg, consumer appliances are sold during holiday and festive seasons. So even if we are not aware of the cause, we can see the patterns in the sales numbers every year. There is no precedent to this pandemic and we do not have sufficient data to detect patterns for this Novel virus.

#### How far ahead can you predict?
We initially started to predict for a 10 days look ahead and are now looking ahead for 20 days. We tried looking ahead for 30 days but did not have sufficient data for the same. But pretty soon we may look ahead for 30 days. Now this look ahead is a high confidence prediction with very good accuracy both in reality and in back test. Then we do a recursive multistep prediction where we feed back our results into the RNN to extend it for longer durations. However the confidence level of these long term predictions is less.

#### How often do you update your predictions?
We update our predictions daily. Every day we have some new true data and these small changes affect the course of the pandemic in huge ways. This is called ‘The Butterfly Effect’ in chaos theory. Hence we have a progressive setup. At the same time we are building and evaluating new models with more inputs and when we find better correlations, we periodically update the models.

#### What good are your predictions if they are changing everyday?
We are not here in a competition to foretell the future accurately. The pandemic has created Chaos and we are trying to make sense of the situation just like everybody else and find if there is some determinism in the Chaos. Our research is far from complete and we are evolving and trying to find more correlations on what makes the curve bend and when. But even with this changing prediction, we think that there is great value in the predictions and we can plan ahead in the future. Unforeseen events such as the lockdowns, the migrant crisis, the ‘black lives matter protests’ and such keep changing the course of future and we believe that our approach is best set to reflect all these changes. We are placing our faith on math and science instead of tarot cards and dice. Neural Networks have been shown in the past to accurately describe highly non-linear variables and we think that they are our best bet to describe the current pandemic.

#### How should we use your predictions?
We think our predictions are very similar to weather predictions. You should look at the short term look ahead and plan your actions according to that. There will be a long term forecast that will keep changing and will keep getting better as they approach nearer. Hence we have designed this interactive app so that you can keep checking back.

[https://seva.ml][sevaml]
[https://covid19india.orgl][covid]
[https://ourworldindata.org][owid]


[sevaml]: https://seva.ml/?utm_source=sevaml&utm_medium=Website&utm_campaign=Third%20Push
[covid][https://covid19india.orgl]
[owid][https://ourworldindata.org]