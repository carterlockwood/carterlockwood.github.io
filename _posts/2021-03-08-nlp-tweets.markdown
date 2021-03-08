---
layout: post
title:  "Twitter and Basic NLP: COVID-19"
author: "Carter Lockwood"
date:  2021-03-08
categories: projects
---

This past fall, one of my professors gave our analytics seminar class a sample of over three million tweets that he had collected between March and October 2020. Each tweet, represented as JSON data, also included geographic tags to document the location of the tweet's origin. One of our tasks as a class was to dig through these tweets and see if we could derive any insights by location from the Twitter data. 

As a lifelong Alabama resident, my initial question was: *'What are the people of Alabama tweeting about?'* 

I created the initial pandas dataframe by reading in the zipped json file containing all of the Twitter data. I then created a new frame for observations containing Alabama within the location columns. 

To get cleaner results, I used the Natural Language Toolkit for some basic tokenization and cleaning tasks (defining multi-word expressions, stemming, lemmatizing, etc.). NLTK has a built in Tweet Tokenizer that is incredibly handly. For each tweet, the text came as a singular string and I deconstructed each into a list of individual tokens that were stored in a new 'Tokens' column. 

After creating the Tokens column, I took it apart it using itertools so that I could use NLTK to find the token frequency distribution. This itertools trick was incredibly handy for taking apart a pandas column of lists.

~~~ python
alabama_tokens = list(itertools.chain.from_iterable(alabama_df['Tokens']))
alabama_freq_dist = nltk.FreqDist(alabama_tokens)
~~~

I used NLTK's built-in FreqDist function to find the token frequency distribution for Alabama. With a little image manipulation trickery, I created an image mask to use in combination with the WordCloud package to generate this image for the distribution:

<img src="{{ '/static/nlp-tweets/alabama_wc.png' | relative_url}}" alt='Alabama WordCloud' >

It looks pretty good, but this data isn't particularly informative. To get a little better grip on exactly what the people are tweeting about, I decided to use NLTK to create bigram frequency distributions from my tokens. Bigrams are just a sequence of two tokens. I also decided to zoom out and look at the United States by region: Southeast, Northeast, Southwest, Midwest, West.

<img src="{{ '/static/nlp-tweets/southeast_bg.png' | relative_url}}" alt='Southeast Bigram Distribution' >

Seven of the top ten bigrams for the southeastern region are comprised of emojis. Within the top five are 'wear_mask' and 'covid_19' which are to be expected during a global pandemic, but there was an unusual presence of elephant-football and wine-rose emoji combinations within this bigram distribution. When I asked my professor why this might be the case, he said it's possible that the Twitter API is filtering tweets differently within our close geographic vaccinity. The results of the other geographic regions were substantially different. 

<img src="{{ '/static/nlp-tweets/other_bg.png' | relative_url}}" alt='Regional Bigram Distributions' >

The top bigrams for each of the other geographic regions are almost entirely pandemic-related. This shouldn't be used as any sort of conclusive finding, but it was fascinating to see such stark differences in tweet content by geographic region in the given sample of tweets.  
