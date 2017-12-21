<!-- TITLE: Elasticsearch -->
<!-- SUBTITLE: A quick summary of Elasticsearch -->

# Installation for Debian
https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html
```wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-6.x.list
sudo apt-get update && sudo apt-get install elasticsearch
```
# Running
`sudo update-rc.d elasticsearch defaults 95 10`

```sudo -i service elasticsearch start
sudo -i service elasticsearch stop
```

# Connection Test
`curl localhost:9200`