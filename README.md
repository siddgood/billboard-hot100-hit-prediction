# Billboard Hot 100 Hit Prediction
Predicting Billboard's Year-End Hot 100 Songs using audio features from Spotify and lyrics from Musixmatch

## Abstract
Each year, Billboard publishes their Year-End Hot 100 songs list, which denote the top 100 songs of that year. The objective of this project was to see whether or not a machine learning classifier could predict whether a song would become a hit *([Hit Song Science](https://en.wikipedia.org/wiki/Hit_Song_Science))* given it's intrinsic audio features as well as lyrics.

## Data & Features
A sample of 19000 Spotify songs was downloaded from [Kaggle](https://www.kaggle.com/edalrami/19000-spotify-songs), which included songs from various Spotify albums. Additionally, Billboard charts from 1964-2018 were scraped from Billboard and Wikipedia.

Using Spotify's Audio Features & Analysis API, the following [features](https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/) were collected for each song: 
- **Mood**: Danceability, Valence, Energy, Tempo
- **Properties**: Loudness, Speechiness, Instrumentalness
- **Context**: Liveness, Acousticness

Additonaly, lyrics were collected for each song using the [Musixmatch API](https://developer.musixmatch.com/documentation/api-reference/track-lyrics-get). I took a bag-of-words NLP approach to build a highly sparse (86%) matrix of unique words.

After cleaning the data, a dataset of approx. 10000 songs was created.

![](images/data-distribution.png)
![](images/fig-vs-decade.png)
![](images/genre-dist.png)

## Exploratory Data Analysis

**Spotify Features over Time**
![](images/acoustic-vs-time.png)
![](images/dance-vs-time.png)
![](images/energy-vs-time.png)
![](images/live-vs-time.png)
![](images/loud-vs-time.png)
![](images/speech-vs-time.png)

The above graphs clearly show that audio features evolve over time. More importantly, the separability of data in certain graphs such as *Acousticness vs. Time* and *Loudness vs. Time* indicates potentially significant features that can help distinguish between the two classes.
