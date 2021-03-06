# Most common words and bigrams in the last minutes per location in Spain

## Description

Given a general election, a shocking news or a football match, the overall reaction can be very distinct in separated places. The aim of this project is finding what people from different Spanish cities thinks about a topic. It will be done by finding the most common words and bigrams in tweets during the last minutes per location. Then, it will be performed a sentiment analysis, and it will be plotted the mean polarity and subjectivity of twe tweets per each city.

## Details

When talking about locations in Tweet data, there are two types: Tweet location and Account location[1]. In this project we will work with the account location, i.e. the 'home' location of the user.

To do so, some problems need to be faced. One of the most importants is identifying which users belong to the same town.

Users location has not a well defined format; locations are highly customizable. To clearly identify the users location, and remove those that do not correspond to the places we are interested or that do not correspond to any place, it is requested a csv file with the name of all the cities of the region. The one we are using is spain_cities.csv[3] (which includes the coordinates of the city for future projects). Below are some account locations found during the project:

Murcia, España
Planet Earth
Barcelona
Barcelona, Spain.
Barcelona, Cataluña
Barcelona, Catalunya
Moralzarzal - Madrid - España
Campillos(Malaga)

There is defined a function called location_filter to identify the original city with such different formats. Feel free to modify it.

In the input folder there is also a file called valid_ends.txt. It is used to deal with the same problem: Finding the users location and make easier to find users from the same place. It is a file with the end of some account locations (such as 'España', 'Spain', 'Cantabria' and so on) to make easier the task.

There is attached an example of an execution of the full notebook. The results are saved inside the output folder. Inside this folder, there a folder for execution. The same of the folder is of the form keyword1_keyword2_..._keywordN_DAY-MONTH-YEAR_HOUR.MINUTE.SECOND.jsonl, where the keywords are the words used to search tweets and the rest is the moment when the execution took place.

Inside the folder you will find:
* keyword1_keyword2_..._keywordN.jsonl: JSON file with the data of the retrieved tweets.
* counter_location.txt: Number of tweets per city.
* words.txt: Top words used in all cities.
* bigrams.txt: Top bigrams used in all cities.
* words_location.txt: Top words used per city.
* bigrams_location.txt: Top bigrams used per city.
* images folder:
    * polarity.png: Image showing polarity per city.
    * subjectivity.png: Image showing subjectivity per city.

With respect to the sentiment analysis, there are not too many tools to perform sentiment analysis in Spanish. In this approach, the tweets  are translated to English and then TextBlob library is used to estimate the polarity and subjectivity of each tweet.

## Requirements

* A Twitter developer account[2]
* Jupyter notebook
* The libraries that are used are specified at the beginning of the notebook. To install a library, run in a new cell:
	pip install <library_name>
	e.g.
	pip install nltk

  The libraries/packages used during the development are the following ones:
	* pandas:     0.23.4
	* numpy:      1.15.4
	* tweepy:     3.10.0
	* json:       2.0.9
	* emoji:      1.2.0
	* nltk:       3.4
	* textblob:   0.15.3
	* matplotlib: 3.1.1
	* cartopy:    0.17.0

## About adapting the code for other countries or languages

The code is thought to be used for tweets in Spanish that are written by users with account location in Spain. If you are thinking about using this code with the same purpose for another country, you must create a cvs with the format with towns of the corresponding region. Moreover, you must modify valid_ends.txt.

To modify the language, you will probably need to modify location_filter and normalize functions to be able to read to cities names and text from the corresponding language. You will also need to modify the stopwords set.

## Contributing
Pull requests and any kind of ideas to improve the code are welcome. Feel free to send pull requests and contact with me.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Author
Name and Surnames: Daniel Roncel Díaz

## References
[1] https://developer.twitter.com/en/docs/tutorials/filtering-tweets-by-location

[2] https://developer.twitter.com/en

[3] Data retrieved from https://www.businessintelligence.info/varios/longitud-latitud-pueblos-espana.html
