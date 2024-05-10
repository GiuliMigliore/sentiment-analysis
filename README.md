# How did the sentiment towards ChatGPT evolve on a daily basis during the first two weeks after its launch?

With this project we tried to understand people's opinions about ChatGPT and highlight the differences in the public opinion, particularly regarding the various languages used. To do this, we applied detailed natural language processing methods to examine comments about the topic on Twitter.

## Sentiment Analysis

[VADER](https://github.com/cjhutto/vaderSentiment) (Valence Aware Dictionary for sEntiment Reasoning) is a rule-based model for general sentiment analysis. It uses a combination of qualitative and quantitative methods to produce, and then empirically validate, a gold-standard sentiment lexicon that is especially attuned to microblog-like contexts such as those observed on Twitter and Facebook.
We applied VADER as a sentiment analysis tool to extract the sentiment of text data in our dataset. Since VADER is designed to handle raw text data, especially informal language, idioms, slang, and even emoticons, which are often used in social media texts, we applied it directly to the text data without any preprocessing steps such as tokenization, stemming, or removal of stop words.

We also applied [K-means](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) clustering to preprocessed textual data with a predetermined number of 3 clusters. We then compared the two methods in the "output" folder of this repository.

## Topic Modeling

To perfrom topic modeling, we used the [Latent Dirichlet Allocation (LDA)](https://towardsdatascience.com/end-to-end-topic-modeling-in-python-latent-dirichlet-allocation-lda-35ce4ed6b3e0) model. LDA assumes each topic is a mix of words and each piece of text is a mix of these topics. 

## Authors

P. Sabournia: [@PejmanSa](https://github.com/PejmanSa)

P.A. van Beek: [@PablovanBeek](https://github.com/PablovanBeek)

K. Kunst: [@Kamielk01](https://github.com/Kamielk01)

G. Migliore: [@GiuliMigliore](https://github.com/GiuliMigliore)