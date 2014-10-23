Assignment: Create a time-series chart (i.e. a column or line chart) or a table showing the number of tweets that mention “Ebola” from Democrats and Republicans.

Tried

SELECT *
FROM tweets
JOIN social_accounts
ON tweets.screen_name = social_accounts.twitter_screen_name
JOIN members
ON social_accounts.bioguide_id = members.bioguide_id
WHERE text
LIKE "%ebola%"


Then exported file as .csv and into Google Spreadsheets

![graph](http://i.imgur.com/aVuOzkD.png)

Initially I wanted to graph by time, but couldn't figure it out. Then I talked to Allison, who told me about =INT to grab integers... worked for her. I'll try next time.

