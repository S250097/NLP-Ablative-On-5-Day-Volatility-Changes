# NLP-Ablative-On-5-Day-Volatility-Changes

A project created in graduate school for the MH6812 module teaching Natural Language Processing.

## Goal: 

Predict daily change in 5-day volatility of the S&P500.

## Architecture: 

Numeric features are input into an LSTM. Text is input into a transformer. The output vectors of both are concatenated and then input into a FFNN to learned the optimal weighting of Tweets and numeric data. We are not optimizing individual modalities in this tri-modal architecture, but rather optimizing the weights and biases of the coupled system as a whole set. 

## Conclusions: 

A transformer trained on a Corpus of Trump's Tweets adds no predictive signal. This is unsurprising and not unprecedented. Daily stock returns are noisy because developed markets like the U.S. are efficient. When information is known, it is quickly priced in, creating reactionary fluctuations to news and sentiments. Existing work shows correlations between past and future log price by Fama [X1] yields extremely low R^2, approaching 0, with a decent number of negative values. In 2019, the Volfefe Index developed by JPMorgan Chase analyzed a corpus of Trump’s Tweets and demonstrated empirically that volatility in U.S. Treasury yields could be statistically linked to Trump’s Tweets. The Index is a measure that tracks this impact on volatility, however it is not a proof or model itself. Klaus and Koser [X2] employed a 20-day rolling-window regression, showing that the Volfefe index’s mean impact across all European markets was not persistent, but the Spanish IBEX35 did show statistically significant exposure. Filippou et al. [X3] however found an equal-weighted average return across bilateral currency pairs was approximately 0.005% in the hour following a tweet, and informative tweets were associated with a decline in intraday foreign exchange spot volatility and trading volume.

## Caveat:  

Ideally in handling time-series data a rolling training and re-training window should be applied. However as the purpose of this class was purely to demonstrate understanding of NLP and that its emphasis was not on finance, a simplistic training on a fixed historical window and testing on future out-of-sample data was applied. 
