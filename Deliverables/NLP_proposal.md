# NLP and Unsupervised Proposal: Steam2 the Redux
Michael Harnett<br>
6/16/21
<HR>

#### <b>Goal:</b> Use natural language processing and topic modeling to understand driving factors behind a video game's success
<hr>

For this project, I have decided to return to Steam, the same data I worked with for my linear regression project. The first time around, I used available numeric and categorical data to try and predict the number of copies owned. I was eventually able to create a highly predictive model, that had a RMSE of below 1. This time around, I would like to process the actual reviews left for the games. I would like to look at the top performing and bottom performing games by genre, and extract popular sentiments behind their success or failure. Ideally, this could be further developed into a recommendation engine, allowing gamers to find new games based on extracted topics, that they may not have found on their own.
<br>
<br>
<Br>
## Data
Where the data for my linear regression project was manually scraped (as directed by the project guidelines), the data this time around will be pulled directly from Steam's API, allowing a more robust, complete set of data. Information is available on a by game basis,  and a by user basis. I will be looking specifically at game review data and overall review scores. There is also ratings for each reveiew, showing if other user's found the review helpful. 
<br>
<br>
<Br>
## Tools 
The bulk of the work for this project will be done in Python:
<ul>
<li>Python's requests and json library will be used to communicate and collect data from Steam's API.</li>
<li> NLTK and spaCy will be used to parse and tokenize the review data.</li>
<li>Several of SKLearn's libraries will be used for modeling, dimensionality reduction and matrix decomposition.</li>
</ul>
<br>
<br>
<Br>
## MVP Goal
For the MVP, I would like a fully clean and tokenized set of reviews for the top 10 and bottom 10 role playing games (RPGs), based on rating. Further EDA will have to be performed to know the appropriate number of reviews per game to use. I aim to have actionable insights and understandings of what topics drive the popular games, and what topics attribute to the negative games downfall. I will then scale this up to include every genre.
