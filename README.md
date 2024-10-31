# Music-Recommendation_System
So the music recommendation system I created runs through algorithms that analyzes data about user interactions with music like their genre preferences, listening history, and skipped tracks. We preprocessed the data using techniques to cleanse and organize the information. Then we used collaborative and content-based filtering to generate music recommendations.

We first go to the developer dashboard and fill out the details to obtain the client ID and client secret and use that data in an encoded format to request the access token. With the access token we can make authorized requests to retrieve music data. We use requests module to send HTTP requests via Python.

We then install a Python library called 'spotipy' that provides access to Spotify's web API where we use OAuth so third parties can gain access using the access token. We create a function that can fetch information about the tracks in the playlist using parameters such as track ID, name, artists, album name, etc and stores it in a dictionary. We also create another dictionary comprising of track attributes like acoustics, energy, tempo, etc. We use this to create a dataframe using pandas for simplify analysis. We then call the function using the playlist ID and access token and display the dataframe to see if our code worked well.

Next, we checked whether the data has any null values and we import the training and testing module from sklearn. We define a function that computes the time span between the release and present day. Recent releases have a higher weight compared to older releases which can show that users prefer newer music more. We then normalize the data.

Next, we created two functions, one for content similarity and another for hybrid similarity.

For the content similarity function, it takes a song name as the input from the user and checks whether it exists in the dataframe. It then calculates the similarity score between the input song and all the other songs in the dataset using cosine similarity and then sorts the similarity score in descending order in a tabular format. 
The hybrid similarity function provides a higher level of personalized recommendations as it considers the content similarity as well as the weighted popularity. 
