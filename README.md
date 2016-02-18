# fezzik

["No more rhymes now, I mean it!"  
"Anybody want a peanut?"]
(https://www.youtube.com/watch?v=DP5-qJSzDUg)

Fezzik searches the Twitter stream to find pairs of rhyming tweets.

## To run locally

- [Create a new Twitter app.](https://apps.twitter.com/)

- Clone this repo locally.

- Install dependencies:
```
pip install flask twitter
```  

- In the home directory of the repo, create a file called `.env` for your keys & tokens (these will be set as environment variables):
```
CONSUMER_KEY=$YOUR_KEY  
CONSUMER_SECRET=$YOUR_SECRET  
ACCESS_TOKEN=$YOUR_TOKEN  
ACCESS_TOKEN_SECRET=$YOUR_TOKEN_SECRET
```
  
- Set environment variables: 
```
set -a
. .env
```
  
- Fezzik relies on the [CMU Pronouncing Dictionary.](http://www.speech.cs.cmu.edu/cgi-bin/cmudict) Set up this dictionary as a local database:
```
sqlite3 /tmp/words.db < schema.sql
python -c 'import data_handler; data_handler.build_db()'
```
