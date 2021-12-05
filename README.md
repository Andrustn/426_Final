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


In order to make the data useable we had to do some cleaning and preprocessing. The first thing we did was remove formating, punctuation, and a tag that was included at the end of each song. Next we removed stop words and lematized the words. Lematizing takes words like start started starting and converts them into the base word, in this case start. Next we tokenized the lyrics so they would be in a format that is useable. We had two methods for doing this. The first method was to count vectorize each word. That created a dataframe in which each row was a song and each column was a word in the dataframe with a count of how many times that word appeared in the song.

The second mehtod used a Tf-idf score. This produces something similar to the first method but instead of a count is now gives each word a weight based on the words frequency in other documents.

Both methods were explored while creating the model. 


## EDA

The follwing tables show five most common words for each genre, excluding words that don't carry a lot of meaning.

<table>
<tr><th>Country </th><th>Pop</th><th>Rock</th><th>Rhythm and Blues</th><th>Rap</th></tr>
<tr><td>

| Word  | Counts |
| ------------- | ------------- |
| Love  | 3,716  |
| Baby  | 2,798  |
| Time  | 2,645  |
| Girl  | 2,455  |
| Unknown  | 1,000  |
  
</td><td>  

| Wod  | Counts |
| ------------- | ------------- |
| Love  | 4,324  |
| Baby  | 2,482  |
| Want  | 1,845  |
| Wanna  | 1,702  |
| Say  | 1,659  |
  
</td><td> 

| Word  | Counts |
| ------------- | ------------- |
| Love  | 4,927  |
| Time  | 3,124  |
| Come  | 2,877  |
| Unknown  | 1,000  |
| Want  | 2,522  |

</td><td>

| Word  | Counts |
| ------------- | ------------- |
| Love  | 11,976  |
| Baby  | 7,442  |
| Time  | 3,539  |
| Want  | 3,332  |
| Come  | 3,225  |

</td><td>

| Word  | Counts |
| ------------- | ------------- |
| N****  | 17,797  |
| B****  | 11,546  |
| F***  | 7,819  |
| S***  | 7,487  |
| Love  | 4,592  |

</td></tr> </table> 
