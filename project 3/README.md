# **Project 3: Reddit API & Classification**

<table> <tr ><td bgcolor = "white"><img src="../images/cmblogo.png" style="float: centre; margin: 20px; width, height: 50px"><td bgcolor = "white"></td>  
    <td bgcolor = "white"><img src="../images/bumblelogo.png" style="float: centre; margin: 20px; width: 50px, height: 50px"></td>
    </table>

## **Problem Statement**

The proliferation of online dating apps since 2013 has revolutionized the <a href='https://www.businessofapps.com/data/dating-app-market/'>online dating industry</a> , where users are spoilt for choice with over almost 20 different apps to choose from.  As part of a consultancy firm offering data-driven analysis and insights to such dating companies, we identify the most frequently-
used words among app users, so that we can determine the most talked-about features for each app, and provide recommendations to our stakeholders to increase their market share. To kickstart our analysis, we turn to one of the most popular social media platforms, Reddit.

With over <a href='https://sg.oberlo.com/blog/reddit-statistics'>430 million monthly active users worldwide</a>, Reddit houses one of the largest social networking communities and is home to a massive 2.2 million subreddits, of which about 130,000 are currently active. In this project, we narrow down our search to subreddits of 2 popular dating apps - Coffee Meets Bagel (<a href='https://www.reddit.com/r/coffeemeetsbagel'>/r/coffeemeetsbagel</a>) and Bumble(<a href='https://www.reddit.com/r/bumble'>/r/bumble</a>). Using Natural Language Processing, we select and train 5 classification models to determine which model has the best performance in classifying posts into their subreddits based on the text the posts contain. The classification metrics - accuracy, recall, precision and specificity - will be used to evaluate the best model's performance.


## **Executive Summary**

Reddit has exploded in popularity since its inception in 2005 and has remained one of the most popular social media communities,  with 58% of its users between the  <a href='https://websitebuilder.org/blog/reddit-statistics/'>ages of 18-29</a> . This is well-explained by the fact that the advent of social media coincided with internet usage gaining widespread adoption among millennials (roughly born between 1982 - 1996). Furthermore, the mobile applications (apps) revolution accompanied the rapid increase in mobile phone ownership due to their accessibility, convenience and general quality-of-life improvements.

The online dating scene eventually rose to prominence and naturally, subreddits for all the dating apps were created where redditors gathered to seek advice and share their experiences. 2 of the most widely-used and text-heavy apps (Tinder was skipped as it was full of images) - Coffee Meets Bagel (CMB) and Bumble - were picked to explore in of this classification analysis.

We began by scraping the 2 subreddits for at least 750 posts to account for the elimination of non-useable posts (images only, no text, etc.). Tinder was an initial pick but as seen from the scraping results below, CMB and Bumble were the next 2 subreddits in line with a significantly higher proportion of useable posts.

Scraping Results (Useable posts as a %)
- Tinder 129/750 = 17% (Not used)
- CMB 691/750 = 92% (Used)
- Bumble 501/987 = 51% (Used)

After extensive data cleaning and text preprocessing through the removal of stop words (common words that are not meaningful in our analyses) and combining the title and text of each post, we explore the word frequencies from each subreddit through the use of word clouds and bar charts. Several keywords stood from the respective subreddits:

- CMB: "discover", "suggested", "bean"
- Bumble: "woman", "dating",

The modelling selection process involved building pipelines consisting of either the CountVectorizer or Term frequency-Inverse document frequency vectorizer, and a classification model. Hyperparameter tuning was then done to obtain the best training and cross-validated scores for each pipeline. From the tuning results, it was determined that the best model is the Multinomial Naive Bayes model via comparisons with the cross-validated score and the accuracy score on the test (validation) data set, which were 77.0 and 73.6% respectively.

The results of the classification metrics are as such:
- Accuracy - 73.6%
- Misclassification rate - 26.4%
- Recall - 76.8%
- Precision - 77.4%
- Specificity - 69.3%

The accuracy score of 73.6% here is not extremely high, suggesting that posts made in the /r/bumble and /r/coffeemeetsbagel subreddits do not differ significantly.

High recall scores show that the model performs better at classifying posts belonging to /r/coffeemeetsbagel compared to classifying posts belonging to /r/bumble. A misclassification analysis was conducted by looking through the misclassified posts to make sense of the 26.4% misclassification rate. A common trend was discovered from the contents of the posts which consisted of users seeking advice on relationships, sharing their dating experiences on the apps, or ranting about scammers. It is understandable that these topics appear in both subreddits as both groups of users are in similar situations and thus, would share similar experiences.

Word importance was also explored by determining the top coefficients of words in the respective subreddit. Words which influenced the classification model the most from CMB include 'liked', 'discover' and 'suggested, while that of Bumble was rather inconclusive with 265 words with the joint-highest coefficient. Closer inspection of these words did reveal several keywords unique to the Bumble app, such as 'bee', 'beeline', 'bi', 'binary' and 'non binary'. However, they did not appear frequently enough for our model to pick up their importance.

These keywords are important because they are features unique to the respective apps, and it is evident CMB has more differentiating factors compared to Bumble, and that Bumble does not have features which are prominent or unique enough.


## **Conclusions and Recommendations**

From our extensive modelling process, we deduce that the CountVectorizer combined with Naive Bayes classification model performs the best in terms of classifying the subreddits. The metrics used to evaluate its performance include:

- Accuracy - 73.6%
- Recall - 76.8%
- Precision - 77.4%
- Specificity - 69.3%

While accuracy provides an overview of this model's performance, the other metrics do offer greater insights to the respective stakeholders. For instance, a high recall and precision rate shows greater success in classifying posts belonging to the CMB subreddit.

In contrast, only 69.3% of posts were correctly classified to be from Bumble.

This is likely a result of the higher amount of special features unique to Coffee Meets Bagel, most notable "discover", "suggested", "liked" and "bean". Although Bumble does have its own special features ("non binary", "gay", "binary", "bi", "spotlight", "bee", "beeline") they appear to not be a strong differentiating factor in our Reddit posts.

Social Considerations:
It is pertinent to note that the expanded range of non-binary gender options may not be a comfortable topic of discussion for mainstream society yet, which could explain why although these terms do appear in the features unique to Bumble, they are not represented in a significant majority of the posts that were scraped.

Therefore, there are separate recommendations for both of these apps:

- Coffee Meets Bagel: The special features of "discover", "suggested", "like" and "bean" are prominent, which lends credence to the belief that more fine-tuning could be placed on them to improve their functionalities to benefit their users.


- Bumble: Although it is praiseworthy that Bumble is extremely inclusive in terms of gender options, perhaps more focus could be placed on enhancing the unique features (i.e spotlight, bee, beeline) to improve user experience. Furthermore, new features could also be implemented to further differentiate itself from other dating apps out there in the market.
