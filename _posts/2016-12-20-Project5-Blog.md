---
layout: post
title: Predicting Loan Repayment
---

## Predicting Loan Repayment Blog

Being that this is the first model I build, there was a huge learning curve.  This process consisted of a lot of trial and error.  First, I imported the file into a DataFrame.  Then I tried to understand the data I had.  Being that there are over 100 columns of data, I had to figure out which columns I would use.  I narrowed down my search by using the categories my professor suggested we use in the instructions.  Once I determined the columns I wanted to use, I created a new DataFrame of just the info I needed.

Since the dataset contained completed loans and current loans, I could only use completed loans to build my model.  I creataed a new column to determine the outcome of all of the completed loans; good or bad.  I dropped the current loans.  Now I needed to clean the data I had so I can analyze it.  This involved normalizing, creating dummy variables, and converting everything to integers and/or floats.

Now I have data that is ready to explore.  This took a lot of trial and error playing with pivot tables and charts.  Some of the trends I noticed were that short term loans had a higher probability of repayment comapred to longer term loans.  The same could be said for home owners comapred to renters.  Another trend I noticed was that the lower the interest rate and dti, the more likely it got paid off.  From this data, I noticed we had about 3 times as many good loans as bad loans.  In order to get an equal number good and bad loans, I took all of the bad loans, and an equal number of good loans and put it into one dataframe.  This gave me an equal probability of good or bad loans.  This set my benchmark at 50% for when I predicted the outcome later.

Now that I have an idea of what model parameters could determine the outcome of the loan and I had a good dataset to work with, it was time to build my predictive model.  First, i created a sigmoid function in order to put the probabilities on a 0-1 scale.  Then, I took the data I needed and converted it into a list of lists.  I created my predictive distribution function using a binomial distribution.  I then added the sum of the predictive distribution for all my data points to the likelihood.  I then ran a sampler and MonteCarlo for each of my input omegas and I calculated the optimal set of each.  Then I plotted the distribution of each of the model parameters.

I then created a function where you can enter any loan and it would predict the probability of the loan being repaid.  I also took the average of 500 good loans (I used 500 to save processing time) and 500 bad loans which tols me how good my model was when comapred to my 50% benchmark.  My model predicted that 73% of the good loans would be repaid, which was well above my 50% benchmark and told me this is a good model to predict good loans. However, my model also predicts that my bad loans also have a high probability of being repaid.

In conclusion, I need to revist my model in order to better determine bad loans while maintaining my good loan predictability.
