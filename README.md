# Python Scraping API for Google results
Google's search result scraping API allows for seamless and fast querying of the search engine. The Python code is simple to implement in your own environment. 
Below is an example of code for scraping Google results [using the ScrapingBee API](https://www.scrapingbee.com/features/google/?fpr=easy-scraping-api).
```
  import requests
  def send_request():
      response = requests.get(
          url="https://app.scrapingbee.com/api/v1/store/google",
          params={
              "api_key": "RAG4HI40ZCRMWSUPEHCW6I1L1Z49K614648WITSYW7GSQKZCSS24RFJMP7AFEFWSQK725ASDVBZ0DTE5",
              "search": "pizza new-york",
          },

      )
      print('Response HTTP Status Code: ', response.status_code)
      print('Response HTTP Response Body: ', response.content)
  send_request()
  ```
  In the response from the API, we receive JSON-formatted data. Depending on the need, we can export the JSON file or create a GSC with results taken from a search engine, such as Google Maps results.
  ```
  {
    "statusCode": 200,
    "body": {
        "meta_data": {
            "url": "https://www.google.com/search?q=pizza%20new%20york&hl=en&gl=us&num=20&start=0",
            "number_of_results": 615000000,
            "location": "",
            "number_of_organic_results": 22,
            "number_of_ads": 0,
            "number_of_page": 7
        },
        "local_results": [{
            "title": "Joe's Pizza",
            "review": 4.5,
            "position": 0,
            "review_count": 5422
        },
        ...
        ],
        "organic_results": [{
            "url": "https://ny.eater.com/maps/nyc-best-iconic-pizza-pizzeria",
            "displayed_url": "ny.eater.com › maps › nyc-best-iconic-pizza-pizzeria",
            "description": "Jan 17, 2020 - Roberto Paciullo's Bronx trattoria serves wood-fired pizzas that have puffy brown crusts and floppy centers. Some pizza geeks think that Zero Otto ...",
            "position": 0,
            "title": "New York City's 27 Most Iconic Pizzerias - Eater NY"
        },
        ...
        {
            "url": "https://www.timeout.com/newyork/restaurants/best-new-york-pizza",
            "displayed_url": "www.timeout.com › restaurants › best-new-york-pizza",
            "description": "Aug 2, 2019 - There's nothing that says “I love NY” more than eating a classic slice of New York pizza in view of the Brooklyn Bridge. And who better to provide ...",
            "position": 17,
            "title": "29 Best Pizzas in NYC for Life-Changing Slices To Eat Today"
        }],
        "top_ads": [],
        "bottom_ads": [],
        "related_queries": [{
            "title": "best pizza new york",
            "position": 0
        },
        ...
        {
            "title": "joe's pizza new york",
            "position": 7
        }],
        "questions": [{
            "text": "What is the best pizza in NY?",
            "position": 0
        },
        ...
        {
            "text": "How much is a slice of pizza in New York City?",
            "position": 3
        }]
    }
}
```
## Customizable Python scraped google results 

The API is flexible, it rotates user-agents by itself, and you can also set geolocation, as well as language depending on which search engine you want to retrieve data from. This reduces the risk of responses returning an error. 
[Check out the demo](https://www.scrapingbee.com/features/google/?fpr=easy-scraping-api).
```
import urllib.parse
encoded_url = urllib.parse.quote("YOUR SEARCH TO SCRAPE")

```
The Python scraping API also allows you to personalize the number of results in Google search. We can also use JavaScript rendering.

## Extract Google search data using CSS selector and Python

If you want to retrieve data without parsing on your side, you can take advantage of Google's result extraction capability via [API Call](https://www.scrapingbee.com/features/google/?fpr=easy-scraping-api). 

```
from scrapingbee import ScrapingBeeClient

client = ScrapingBeeClient(api_key='YOUR API KEY')
response = client.get(
    'https://www.google.com/search',
    params={
        'extract_rules':{"result title": "h3"},
    },
)
print('Response HTTP Status Code: ', response.status_code)
print('Response HTTP Response Body: ', response.content)
```
Google scraping API can be used to collect data from Google search results, Google Maps, Google News or Google Images.

  
