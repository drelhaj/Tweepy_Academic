# Tweepy_Academic
Search and download tweets from Twitter using Tweepy and Twitter API v.2. 
The code works with [Twitter API Academic Research Access](https://developer.twitter.com/en/products/twitter-api/academic-research), which has a limit of 10 million tweets a month and allows full archive search, back to March 2006.

# Functions
The code allows the following: 
- searching Twitter's full archive
- the use of a query combined with a search location (e.g. "COVID-19" in UK [GB])**
- the use of Tweepy Paginator 
- saving output to a CSV file
- predection of sentiment (psoitive, negtive, neutral) using TextBlob
- sleeps to avoid error: 429 Too Many Requests

# Tweitter fields extracted:
- [Tweet](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user):
  - ID (default). String. The unique identifier of the requested Tweet.
  - text (default). String. The actual UTF-8 text of the Tweet. See twitter-text for details on what characters are currently considered valid.
  - geo. Object. Contains details about the location tagged by the user in this Tweet, if they specified one.
  - created_at. date(ISO 8601). Creation time of the Tweet.
  - public_metrics. Object. Public engagement metrics for the Tweet at the time of the request.
    - retweet_count (how many times it was retweeted [shared])
    - like_count (how many times it received a heart [like])
    - quote_count (how many times it was retweeted with a quote [shared with a comment])
    - reply_count (how many people replied to that tweet)  
- [User](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user): 
  - id (default). string. The unique identifier of this user.
  - location. string. The location specified in the user's profile, if the user provided one. As this is a freeform value, it may not indicate a valid location, but it may be fuzzily evaluated when performing searches with location queries.
- Extra:
  - Mentions: extracts mentions following the @ sign.
  - Hashtags: extracts hashtags following the # sign.
  - URLs: extracts URLs
  - Sentiment: using TextBlob it gives you a prediction of the tweet's sentiment.
