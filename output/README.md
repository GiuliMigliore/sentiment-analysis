## Sentiment Analysis

### VADER

The VADER sentiment analysis model outputs a normalized score that ranges from -1, representing a strong negative sentiment, to 1, which reflects a strong positive sentiment.
The average VADER sentiment score is approximately 0.187 for the English tweets, 0.174 for the Spanish tweets, and 0.193 for the French ones. 

In the VADER section of the "script.ipynb" file, the histograms of VADER sentiment scores display a notable concentration of scores at 0 across all three languages, which suggests that a good number of tweets convey neither a positive nor negative sentiment. On both ends of the central peak, the tweet frequency diminishes toward the extremes of the spectrum, indicating a minimal number of tweets with highly positive or negative connotations. However, there is a higher occurrence of texts on the positive side of the spectrum compared to the negative side. This asymmetry between the positive and negative sides of the histogram can be interpreted as an overall positive sentiment toward ChatGPT during the provided time interval among the users included in the dataset.

From the 7-day rolling average of the VADER score, it is visible that the sentiment expressed in tweets has remained relatively stable over the given period for all three languages analyzed. This indicates a balance between positive and negative sentiments in the dataset over the given period, and despite daily fluctuations, which may reflect reactions to specific events or news, the 7-day trend lines suggest no variation in sentiment in all three languages.

### K-means

We also applied K-means clustering to preprocessed textual data with a predetermined number of three clusters. Cluster 2 is represented by purple points, and clusters 0 and 1 are represented by green and yellow points. The distribution of texts across the clusters is highly skewed, with the majority of texts (91.25%) falling into cluster 2, while clusters 0 and 1 comprised only 3.9% and 4.8% of the data, respectively. The mean VADER sentiment score is used as an external validation tool to indicate the sentiment within each cluster. Cluster 2 has a mean VADER score of 0.204, suggesting a majority of positive sentiment within this group. Clusters 0 and 1 have mean VADER scores of 0.012 and 0.005, respectively, representing a neutral sentiment overall.
These results show that cluster 2 contains texts with mainly positive sentiments, while clusters 0 and 1 seem to contain texts with sentiments that are mainly neutral. The close to zero mean VADER score for both clusters 0 and 1 raises the concern about the sensitivity of K-means in distinguishing between different sentiments. To further investigate this, the Silhouette score was calculated with the resulting score of 0.314, which shows that there are no clear cuts between clusters. This could be influenced by factors such as the number of features and the nature of text data. This phenomenon reflects the complexity of sentiment analysis when it comes to social media texts and it highlights the need for human-centric approaches such as VADER.

## Topic Modeling

The parameters of the LDA algorithm have been set to produce a sum of 40 topics. The topics derived from Spanish and French tweets have been kept in their own language and manually translated using Google Translate only after the topic modeling selection. For the entire list of topics, weights and languages, see "topics.txt". Below the most common topics for each language are listed.

English:
-	Google
-	Data
-	Artificial intelligence
-	Netflix
-	AWS or other cloud services.
-	Elon Musk 
-	Blockchain.

Spanish:
-	Artificial intelligence
-	Autopilot for programmers
-	Generative AI imagination

French:
-	Artificial intelligence
-	Adamgopass
-	Google

The topics generally seem to be concerning terms within information technology, with a focus on artificial intelligence. The English terms appear to be more detailed than their Spanish and French counterparts, probably because the alternative languages have a significantly smaller sample size compared to the English one.

## Ethical considerations

It is a recommended practice to consider potential ethical concerns when studying social media content. In this project, the research poses no harm. Being Twitter a public platform, users have already consented to the platform's privacy policy by agreeing to its terms and conditions. 

It's crucial to recognize that Twitter data may not accurately reflect the entire population, as many individuals choose not to share their thoughts and opinions on this platform. Additionally, one should acknowledge that the Twitter API has the capability to screen out particularly negative or toxic messages, potentially influencing the outcomes of our analysis.

## Limitations and Future Research

Some limitations should be considered when interpreting these results. An important constraint arises when relying on automated translation services like Google Translate, which was used to translate the Spanish and French tweets to then assess their sentiment. Despite its notable improvements, Google Translate frequently fails to capture the nuances of language, such as idioms, and irony, potentially impacting the sentiment conveyed in a sentence. Therefore, performing sentiment analysis with VADER, which is primarily designed for English text, may not accurately reflect the true sentiment when applied to translated tweets.

Another factor to take into account is the use of rule-based lexicons like VADER. Lexicons are hard to scale since updates are required whenever new keywords and idioms are identified. Moreover, this approach might lack accuracy when dealing with sentences influenced by diverse cultural contexts.

Moreover, it's important to note that the dataset utilized for our investigation focuses solely on tweets that were published during the first two weeks after the launch of ChatGPT. The sentiments expressed during this period could be affected by the initial excitement and may not reflect an impartial sentiment observable over a more extended time frame. 
For a more accurate response to the research question addressed in this paper, it is advisable to investigate sentiment trends across a more extended timeframe. Additionally, when analyzing multiple languages, acquiring additional data from these languages can be advantageous. Lastly, considering that not everyone utilizes Twitter, it is advisable to explore alternative research methods when studying public opinions.