# tweetmineR

Mine and analyze tweets in R using TidyVerse tools and TAGS archiver for Google Drive.

See my blog post, ["Mining Twitter data with R, TidyText, and TAGS"](http://pushpullfork.com/2017/02/mining-twitter-data-tidy-text-tags/), for detailed instructions and examples.

## Instructions (TAGS)

To use this script, first generate a [TAGS archive](https://tags.hawksey.info/) of the tweets you want to mine. Then publish a CSV version of the ```Archive``` page to the web or download it locally.

In ```mine_tweets.R```, add the url or local path for that CSV file to the line:

    google_sheet_csv <- ''

Then you can run the script in R studio chunk-by-chunk.

This script will tell you the following:

- What are the most common words in a Twitter archive?  
- What are the most common URLs posted in a Twitter archive?  
- What are the root domains of the most common URLs in that archive?  
- For archives generated from multiple sources, what are the most characteristic domains linked from those different archives?

The script will follow redirects from the ```https://t.co/``` URL shortener to find the source URL and domain. Because this process takes a long time, it will only run on URLs that occur with a frequency above a threshold set at the beginning of the script (```minimum_occurrences```; default is 5).

## Instructions (Python & Tweepy)

```twitter_stream.py``` is a Python script that uses Tweepy to fetch a live stream of tweets based on a search string. Register for a Twitter developer account and add your authentication details at the beginning of the script. To start, either edit the following lines with your search query and output file name

```else:
    search_query = ['fox']
    filename = 'fox_test.csv'```

or call the script from the command line with the following format:

```python twitter_stream.py "['fox']" fox.csv```

(To stream all tweets containing the word 'fox' and output to file `fox_test.csv`.)

Press CTRL-C to stop the script.

More features and details coming soon...

Happy mining!
