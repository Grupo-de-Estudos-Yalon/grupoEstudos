Para esse projeto do web scraping eu tava pesquisando e achei uma biblioteca / framework massa chamado scrapy!

O ponto inicial é a partir do que se chama "seed"

exemplo de código:

```python
from urllib.parse import urljoin

import scrapy

  

class GeniusSpider(scrapy.Spider):

    name = 'genius'

    start_urls = ['https://genius.com/artists/Parcels']

  

    def parse(self, response):

            songs_urls = response.css('div.mini_card_grid-song a::attr(href)').getall()

            print("!!!!!!!!!!!!!!!!!!!!!!",songs_urls)

            for song_url in songs_urls:

                yield scrapy.Request(url=song_url, callback=self.parse_lyrics_page)

  

    def parse_lyrics_page(self, response):

            title = response.css('h1 > span::text').get()

            song_metadata = response.css('div[data-lyrics-container="true"]::text').getall()

            artists = set(response.css('a[href="https://genius.com/artists/Parcels"]::text').getall())

            lyric = response.css('div[data-lyrics-container="true"]::text').getall()

            annotations_ids = response.css('a::attr(annotation-fragment)').getall()

  

            item = {

                'title': title,

                'artists': artists,

                'lyric': lyric,

                'metadata': song_metadata,

                'snippet_lyric': [],

                'annotations': []

            }

  

            if annotations_ids:

                return self.get_annotations(response, annotations_ids, item)

            else:

                return item

  

    def get_annotations(self, response, annotations_ids, item):

        for annotation_id in annotations_ids:

            url = urljoin(response.url, annotation_id)

            yield scrapy.Request(

                url=url,

                callback=self.parse_annotation_page,

                meta={'item': item}

            )

    def parse_annotation_page(self, response):

        snippet_lyric = response.css("meta[property='og:title']::attr(content)").getall()

        annotations = response.css("meta[property='og:description']::attr(content)").getall()

        item = response.meta['item']

        item['snippet_lyric'] = snippet_lyric

        item['annotations']= annotations

  

        return item
```

