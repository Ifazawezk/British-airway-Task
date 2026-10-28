# British Airways review analysis

What do passengers say about British Airways? This project scrapes 1,000 customer reviews from [airlinequality.com](https://www.airlinequality.com/airline-reviews/british-airways), cleans the text and scores the sentiment of each one.

## Result

| Sentiment | Reviews | Share |
|---|---|---|
| Positive | 480 | 48% |
| Negative | 412 | 41% |
| Neutral | 108 | 11% |

Opinion is split almost evenly: slightly more passengers are positive than negative, and few reviews are neutral.

## Steps

1. **Scraping** (`scraping BA.ipynb`): `requests` and `BeautifulSoup` collect 10 pages of 100 reviews each and save them to CSV.
2. **Cleaning** (`Procesisng Data.ipynb`): removes the verification tag before each review, plus special characters and numbers.
3. **NLP pipeline** with NLTK: tokenizing, part-of-speech tagging, stop-word removal and lemmatization.
4. **Sentiment**: VADER compound score for each review (positive ≥ 0.5, negative < 0, neutral in between).
5. **Charts**: a pie chart of the sentiment split and a word cloud with matplotlib and `wordcloud`.

## Run it

```bash
pip install pandas requests beautifulsoup4 nltk vaderSentiment matplotlib wordcloud
```

Open `scraping BA.ipynb` first to build `BA_reviews.csv`, then run `Procesisng Data.ipynb`.
