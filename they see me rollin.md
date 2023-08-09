Para esse projeto do web scraping eu tava pesquisando e achei uma biblioteca / framework massa chamado scrapy!

O ponto inicial é a partir do que se chama "seed"

exemplo de código:

```python
import scrapy

class GeniusSpider(scrapy.Spider):
    name = "genius"
    start_urls = ['https://genius.com/artists/Rainbow-kitten-surprise']
```

