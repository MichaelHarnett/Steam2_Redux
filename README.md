# Steam 2 The Redux
NLP and Unsupervised Project for Metis
<br>
Michael Harnet
<br>
2021
<br>
<br>
<br>
This is a working notebook and is subject to change.
<hr></hr>

### Description of Files included:
<ul>
  <li><b>prelim_work:</b> This notebook is my first notebook used. I explored how Steam's API worked, while also testing the various NLP methods we learned, including CountVectorizer TfidfVectorizer, LSA, and NMF.</li>
  <li><b>scraping_notebook:</b> The final notebook used to create my corpus. A combination of scraping SteamPowered.com and pulling reviews from Steam's API </li>
  <li><b>model_testing:</b> Used for hpyer-parameter tuning on final corpus, to extract most useable number of coherent topics.</li>
  <li><b>recommender:</b> Used to take the topics, and create a recommendation engine, where you input a string, and it recommends games based on the modeled topics
</ul>
<hr></hr>
  
For this Metis module, we are focused on natural language processing and unsupervised learning. I thought it would be fun to re-visit Steam. As opposed to building a linear regression model, this time I am to create a recommendation engine, based on topics extracted from reviews for the most popular games in each genre. 


<hr></hr>
<hr></hr>


## Abstract
<hr></hr>
By analyzing the reviews of the most popular games offered by Steam, developers can understand the driving forces behind successful games. In addition to these insights, Steam can expand their recommendation system to expose gamers to titles they may not have looked at in the past. This would increase visibility for developers on Steam, while increasing Steam's opportunities to sell more games.
<br>


## Data
<hr></hr>
Data for this project was collected in two stages. First, Selenium and Beutiful Soup were used to collect a list of the 30 top rated games for each of their 10 listed genres. This list was then used to pull review information from SteamWorks API. SteamWorks is the division of Steam that helps developer integrate their games onto Steam's platform. I requested the top 100 reviews for each game title; however, not all games had that many reviews, some had only 1. My final corpus was 241 unique games, and slightly more than 100 thousand unuiqe reviews.
<br>


## Tools and Algorithms
<hr></hr>
In addition to BeutifulSoup and Selenium (and of course Python), NLTK was used to tokenize and lemmatize the corpus. Regex was used to remove unwanted words and characters as well. Once my data was sufficiently cleaned, Several SKLearn methods were used. I tried both CountVectorizer and TfidfVectorizer to see which worked better, bot with an LSA (Truncated SVD) model and NMF model. Final model used was TF-IDF with NMF, 11 componetns, minimum document frequency of 3, regex to not only clean but thow out words less than 4 letters, and many additional stop words were added. 
WordCloud and StyleCloud were used to better visualize my topics.
Similarity metrics such as pairwise_distances, using cosine similarity, were used to recommend games based on text imput.
<br>


## Results and Future Work
<hr></hr>
I was able to get a basic recommendation system working, one that takes a string and finds the top 5 reviews that are most closely related based on the modeled topics, and returns the game that review is from. In the future, I would like to make an interactive app to show the work in action. I would also like to scale up the number of games, right now only the 241 games from my data can be recommended, I would like to see how more games and more reviews alter the topics.
