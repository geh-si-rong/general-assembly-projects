# **Project: Algo-Rhythms**
## **The Spotify Song Popularity Predictor & Song Recommender System**

## **Introduction**

Founded in 2006, Spotify is a digital music and podcast streaming service that allows users to access its massive library of over 70 millions of songs and other content from all over the world. As of end 2020, <a href="https://www.businessofapps.com/data/spotify-statistics/">Spotify</a> holds the title of the world's most popular music streaming platform with 345 million users (of which 155 million are paying subscribers), generating USD 9.5 billion in revenue that year.

One key reason propelling Spotify to dominance in the music streaming space was their "Discover Weekly" feature which was fully designed via a machine learning algorithm to generate a curated playlist of 30 songs tailored to the listening habits of the user. Through the use of a collaborative filtering recommender system, the algorithm was equipped to examine playlists of other users to identify similarities among the songs and then recommending similar songs that match the musical profile to the user. Since then, Spotify continuous innovation and refinement of their algorithms through the massive amounts of data collected from their listeners have helped them implement new features such as "Daily Mixes", "Release Radar" and "Playlist Radio", through <a href="https://www.analyticssteps.com/blogs/how-spotify-using-big-data">variations</a> of its highly successful recommender system.

However, despite their numerous algorithm-designed features for their users, we can still gain a lot more insights from their enormous database of tracks to benefit both music creators and music listeners alike.

## **Problem Statement**

The aims of this project are two-fold:
- Predict the popularity of a song based on its musical features (eg. acousticness, energy, tempo, etc) to identify the ideal blend of features characteristic of popular songs.
- Based on the key music features, build a song recommender system that returns a playlist of 30 songs with musical features similar to a particular genre (eg. newcastle nsw indie). A subset of the top 30 genres will be selected to test out the recommender system and shared with other Spotify users to get feedback on how similar the songs in the playlist are.

## **Executive Summary**

The Kaggle Spotify Dataset consists of over 170,000 tracks, including songs, audiobooks and podcasts. As of 29 April 2021, the most updated dataset (version 15) consists of around 600,000 tracks, so to access the dataset I used in this project, do use version 11 found <a href="https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks/version/11">here.</a>

There are 2 main files explored in this project:
- Data: consisting of all songs, their musical features, popularity score and release date
- Data by genres: consisting of all genres and the average score of the musical features of all songs belonging to these genres.

More emphasis was placed on the cleaning and exploration of the data file as it contained all songs with our target variable (popularity). We began by dropping all duplicated songs with the same ID and musical features, as well as removing audiobooks, podcasts and <a href="https://www.whathifi.com/features/25-best-tracks-testing-bass">bass testing songs</a> from the dataset as we do not want these to influence the modelling and song recommendation processes. In addition, given that most recent songs typically have a duration of up to <a href="https://www.dancemusicnw.com/science-behind-shorter-songs-2019/">5 minutes</a>, it was decided that songs which are too long would be dropped as well (the song November Rain - 8.93 mins was used as our reference point to provide some variety in the model). With this, the initial 175,000 songs was reduced to around 160,000.

For the data analysis process, the key musical features (acousicness, danceability, energy, instrumentalness, liveness, loudness, speechiness, tempo and valence) over the years to ascertain their relationship with a song's popularity, and to determine how music has evolved over the decades. After conducting time series analysis on these features, these relationships became more pronounced and we were able to obtain more meaningful results.

To provide context on how Spotify calculates the "popularity" score: "The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are" (<a href="https://help.musicinsights.com/hc/en-us/articles/360049246653-What-is-the-Spotify-Popularity-Score-#:~:text=The%20score%20is%20received%20from,how%20recent%20those%20plays%20are.">source</a>). Thus, it would be expected that recent songs would by and large have a higher popularity score compared to older songs (eg. from 1920s/1930s). We want the popularity to be based off muscical features purely, thus the "year" feature was dropped from the modelling process. Finally, an arbitrary threshold of 0.70 was set as the minimum for a song to be considered "popular". This made up only 2.6% of our dataset.

The following features considered were: 'acousticness', 'danceability', 'duration_mins', 'energy', 'instrumentalness', 'liveness', 'loudness', 'speechiness', 'tempo', 'valence'

These were then fed into the modelling process. To account for the imbalanced classes, we re-sampled the positive popular classes using SMOTE. The models used were:

- Logistic Regression
- K Nearest Neighbors
- Random Forest
- XGBoost

Hyperparameter tuning was done to obtain the best training and cross-validated scores for each pipeline. We then used the best model to find the classification metrics and compared them against an AUC (Area Under The Curve) ROC (Receiver Operating Characteristics) curve to determine the model's ability to distinguish between popular and non-popular songs. Due to the immense size of the dataset, the dataset was broken up into 2 parts (1980 to 1999, and 2000 - 2021) to gain a clearer picture of which musical features contributed to the popularity of songs in the last 40 years.

Finally, the song recommendation system was built on a smaller subset of the dataset - only songs from 2000 onwards were used, giving us around 36,000 songs. This was due to computational constraints (over 200GB of RAM required for 160,000 songs), as well as the fact that the more recent songs were created with better thought and instruments, and are generally more diverse.

## **Data Dictionary**

These features and their descriptions are taken from <a href="https://developer.spotify.com/documentation/web-api/reference/#objects-index">Spotify</a>.

|Feature|Type|Description|Measure
|:---|:---|:---|:---|
|**Acousticness**|Float|A confidence measure of whether the track is acoustic. 1.0 represents high confidence the track is acoustic|0.0 to 1.0|
|**Danceability**|Float|How suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity|0.0 to 1.0|
|**Energy**|Float|Perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.|0.0 to 1.0|
|**Duration_mins**|Float|Song length in minutes|----|
|**Instrumentalness**|Float|Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.|0.0 to 1.0|
|**Valence**|Float|A measure describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry|0.0 to 1.0|
|**Popularity**|Integer|Popularity of a track|Minutes|
|**Tempo**|Float|The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.|0.0 to 100|
|**Liveness**|Float|Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live.|0.0 to 1|
|**Loudness**|Float|Overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude).||-60 to 0 db.
|**Speechiness**|Float| Presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks|0.0 to 1.0|
|**Year**|Integer|Year song was released|1920 to 2021|
|**Mode**|Integer|Indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0| 0=minor, 1=major)|
|**Explicit**|Boolean|Whether or not the track has explicit lyrics|True = yes, False= No|
|**Key**|Integer|Key the track is in. Integers map to pitches using standard Pitch Class notation|0 to 11|
|**Artists**|Object|The artists of the album|---|
|**release_date**|Object|Date album was first released (yyyy-mm-dd)|1920 to 2021|


## **Evaluation and Conclusions**
