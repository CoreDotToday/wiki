<!-- TITLE: Elasticsearch -->
<!-- SUBTITLE: A quick summary of Elasticsearch -->

# Installation for Debian
https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html
```
sudo apt-get install openjdk-8-jdk
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-6.x.list
sudo apt-get update && sudo apt-get install elasticsearch
```
# Running
부팅 시 자동으로 실행되도록 등록하기
`sudo update-rc.d elasticsearch defaults 95 10`

수동으로 시작, 중지, 재시작
```sudo -i service elasticsearch start
sudo -i service elasticsearch stop
sudo -i service elasticsearch restart
```

# Connection Test
`> curl localhost:9200`
{
  "name" : "hSTZhNF",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "TyaNhlw7QUGTjT0l8NIYXQ",
  "version" : {
    "number" : "6.1.1",
    "build_hash" : "bd92e7f",
    "build_date" : "2017-12-17T20:23:25.338Z",
    "build_snapshot" : false,
    "lucene_version" : "7.1.0",
    "minimum_wire_compatibility_version" : "5.6.0",
    "minimum_index_compatibility_version" : "5.0.0"
  },
  "tagline" : "You Know, for Search"
}

# Plugin Management
*/usr/share/elasticsearch/bin/elasticsearch-plugin*
## X-pack

```
sudo bin/elasticsearch-plugin install x-pack
```
## Eunjeon

```
# https://bitbucket.org/eunjeon/seunjeon/raw/master/elasticsearch/
bash <(curl -s https://bitbucket.org/eunjeon/seunjeon/raw/master/elasticsearch/scripts/downloader.sh) -e 6.1.1 -p 6.0.0.1
sudo bin/elasticsearch-plugin install file://`pwd`/elasticsearch-analysis-seunjeon-6.0.0.1.zip
```

# Tutorial
## Index
### Create Index
`curl -XPUT 'localhost:9200/new-index?pretty'`
{
  "acknowledged" : true,
  "shards_acknowledged" : true,
  "index" : "new-index"
}

### Delete Index
`curl -XDELETE 'localhost:9200/new-index?pretty'`
{
  "acknowledged" : true
}

### Mapping
`curl 'localhost:9200/new-index/_mapping/group?pretty'`



## _search
>GET /_search

>GET /index/_search

>GET /index/type/_search

> POST /_search
>{
>  "query": { ... }
>}


## match_all
> GET /_search
>{
>  "query": {"match_all": {}}
>}

## match
>GET /_search
>{
>  "query": {"match": {"field_name": "키워드"}}
>}


## Select the Output
>GET /_search
>{
>  "fields" : ["field_name_0", "field_name_1"],
>  "query" : {
>    "term" : {"field_name_0": "키워드"}
>  }
>}


## Pagination
>GET /_search
>{
>  "from": 0,
>  "size": 10,
>  "query" : {
>    "term" : {"field_name_0": "키워드"}
>  }
>}


## Sorting
>GET /_search
>{
>  "sort": [
>    {"date_0": {"order": "asc""}},
>    {"date_1": {"order": "desc""}},
>    "_score"
>  ],
>  "query" : {
>    "term" : {"field_name_0" : "키워드"}
>  }
>}


## Highlight
>GET /_search
>{
>  "query": {
>    "match": {
>      "field_name_0": "키워드"
>    }
>  },
>  "highlight": {
>    "fields": {
>      "field_name_0": {}
>    }
>  }
>}


