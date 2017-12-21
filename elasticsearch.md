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
부팅 시 자동으로 실행되도록 등록하기
`sudo update-rc.d elasticsearch defaults 95 10`

수동으로 시작, 중지, 재시작
```sudo -i service elasticsearch start
sudo -i service elasticsearch stop
sudo -i service elasticsearch restart
```

# Connection Test
`curl localhost:9200`