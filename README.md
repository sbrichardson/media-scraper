# Media Scraper

`media-scraper` scrapes all photos and videos in a web page. 
It supports general-purpose scraping as well as SNS-specific scraping. 


##### General-purpose Scraping

The general media scraper scrapes and downloads all photos and videos 
in all link `<a/>`, image `<img/>` and video `<video/>` elements of a web page. 


##### SNS-specific

Currently there is the **Instagram** scraper, 
which crawls all posts of a user and downloads media in each post. 


## Installation

Clone the `media-scraper` git repository.

```bash
git clone https://github.com/elvisyjlin/media-scraper.git
cd media-scraper
```

Install Python 3 (at least 3.5) and get all dependencies.

```bash
pip3 install -r requirements.txt
```


#### Web Driver

`media-scraper` loads the content of a web page by web driver (PhantomJS). 
The needed web driver will be downloaded automatically when it is used.


## To Scrape

```bash
python3 -m mediascraper.general [WEB PAGE]
```

The media will be stored in the folder `download/general`.

```bash
python3 -m mediascraper.instagram [USER ID]
```

The media will be stored in the folder `download/instagram`.


## To Import


### Media Scraper


#### General

```python
import mediascraper
scraper = mediascrapers.MediaScraper()
scraper.connect(WEB_PAGE)
scraper.scrape(path=SAVE_PATH)
```


#### Instagram

```python
import mediascraper
scraper = mediascrapers.InstagramScraper()
scraper.username(USERNAME)
scraper.scrape(path=SAVE_PATH)
```


### Parameters of Scraper

Parameter | Description | Default Value
--- | --- | ---
scroll_pause | the pause interval when scrolling| `0.5`
mode | `'silent'`, `normal'` or `'verbose'` | `'normal'`
debug | print debugging message if `True` | `False`