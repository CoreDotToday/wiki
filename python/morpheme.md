<!-- TITLE: Morpheme -->
<!-- SUBTITLE: A quick summary of Morpheme -->

# 형태소 분석기
## Mecab-ko
- http://eunjeon.blogspot.kr/
- https://github.com/koorukuroo/mecab-ko
- https://github.com/koorukuroo/mecab-ko-web

## NLTK
```
$ pip install -U nltk
$ python
```

```
>>> import nltk
>>> nltk.download()
Downloader> d
Identifier> all
Downloader> q
>>> res = nltk.pos_tag(texts)
>>> print(res)
```
