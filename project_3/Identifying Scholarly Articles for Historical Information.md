### Identifying Scholarly Articles for Historical Information

Ever read through articles and then realised you have just wasted your precious time which could have been better used to beat that report deadline? The internet is full of information and articles. How are we able to abstract the relevant articles and discussions pertaining to our study of history without being dragged into trivial or just-for-fun discussions? My team has designed a classification model which will assist your scholarly quest for historical information online. 

---

#### Data

Reddit is an online platform for discussions with multiple subreddits for likeminded people to post their questions and share their ideas. It is also a great place to obtain huge (and free) amount of data with the help of reddit's json api. We have selected 2 subreddits, History and No Such Thing as Stupid Questions to train and build our model. 

Reasons why we have picked these 2 subreddits:
The posts are of similar format. Most of the posts in respective threads start off as a question but differ in terms of content. Texts in History are more 'Historical' while texts in No Such Thing as Stupid Questions are more general and random. They are also popular subreddit threads which allow us to get a balanced data set of about 1000 posts from each thread. This allows us to have a baseline model of about 50%. 

---

### Exploratory Data Analysis

We have identified the top 20 words from each subreddit and found that there exists few common words with high occurences in both subreddits such as 'like','just' and 'people'. Since their numbers are pretty high in both History ('like': 404, 'just': 317, 'people': 357}) and NoStupidQuestions ('like': 335, 'just': 307, 'people': 236). It is likely that these words will not be taken into account for classification as inclusion does not offer distinction between the 2 subreddits.

---

### Modelling



---

## Rubric

