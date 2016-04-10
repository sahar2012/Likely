# Likely
## A Facebook Web App to predict number of likes on a post <br>

## OBJECTIVE <br><br>
To develop a Facebook web application to predict ‘likes’ on your newly created posts based on data from your previous posts.
## APPROACH <br><br>
1. A set of 200 past posts is used as the data set from training our system, testing and then implementing the real world.
The training data set consists of 180 elements, while the testing data set consists of 20.
2. All the stopwords are removed from the posts and raw status is used for analysis and prediction as stop words can hinder the prediction algorithm.
3. The prediction Algorithm is broken down into two types of Analysis: 
  1. *Frequency Analysis*: This analysis corresponds to the power of a word in the given status who likes are to be predicted. Firstly, the TF-IDF value of each of the words in calculated and is then multiplied with the average likes on that word, which is  calculated from the training dataset. This value is summed over all the words in the status. This forms our first parameter in the number of likes.
  2. *Time Analysis*: It is often noticed in Social networks that the time at which a post is created makes a difference in the number of likes, because of the traffic present on the site at that time. The day is broken down in 24 time slots, each of one hour and the average number of likes are calculated in that time frame. The average number of likes in the hour in which the post that is to be predicted in created becomes our second parameter for prediction.
5. Once we have our two parameters, we take the weighted average of the two. 
Likes = (0.095*FrequencyAnalysis) + (0.05*TimeAnalysis)
These become our predicted number of likes.
6.  There are 3 options to use this app:
Login FB User - A facebook user can login through his account, and find the predicted likes on his status which will be entered in our app. 
Testing Data - This displays the results of the algorithm which was trained by a dataset of 180 posts on 20 posts which were used for testing.
New Status - The user can enter any status and likely will predict the number of likes for it.
RESULT
We took different sets of 20 posts for testing and the rest 180 for training our app; on an average we got 67.56% of the posts within ±5 range of the actual value. The discrepancies were mostly noticed in the posts which were quite Random, posts which are very unique from all the other posts. For eg: “Nalin Gupta changed his profile picture”, was a one time occurrence in the 200 posts, and had 6 times the likes than any other post. Such random occurrences could not be predicted correctly. 
MILESTONES
Implemented TF-IDF Algorithm
We were successfully able to implement the TF-IDF algorithm. The basic structure we used to implement the algorithm was: 
tfidf (t,d,D) = tf (t,d) x idf (t,D)
tf (t,d) = occurrences of t in dtotal terms in d
idf (t,D) = logN|dD : tT|
where N is the number of Documents in the corpus.
FBAuth Integration
FBAuth has been implemented as well. Any user can login with our app, and we will get an access token linked to the user's Facebook Information. This is then used to prompt the user to write a status and consequently predict the likes on it based on the previous data. [Note: This will not be working right now and FB has blocked our app and did not grant permissions].

