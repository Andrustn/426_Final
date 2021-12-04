# Song Genre Classification

## Introduction

Music genre help listeners comb through an almost endless amount of music to find songs that they enjoy. There are lots of factors that go into deciding what genre a piece of music falls into. Some of these factors include rthyem, tempo, lyrics, and artist. Given this we were interested in seeing weather a song' genere can be identified by its lyrics alone. Also since genre is much more a fluid concept and some songs fall into multiple genres we want to see how many genere groups an unsupervised learning method think exists.

## Data Collection and Cleaning

In order to answer this question we needed lots of song lyrics with a genre associated with each song. To do this we used [genius' api](https://docs.genius.com/) which contains a wide variety of song lyrics from almost every possible genre. Since there are so so many genres a even more sub genres we decided to choose five to see if our model could distriguish between just those five. The genres we selected were country, rock, rap, rhythm and blues, and pop. To select songs for these five genres we looked up the top 50 artists in each genre and pulled their top 50 songs, if they had that many. If an artist was in two different genres we threw them out all together. In the end the number of songs per each genre were

| Genre  | Counts |
| ------------- | ------------- |
| Country  | Content Cell  |
| Rock  | Content Cell  |
| Rap  | Content Cell  |
| Rhythm and Blues  | Content Cell  |
| Pop  | Content Cell  |


In order to make the data useable we had to do some cleaning 
