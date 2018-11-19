<!-- TITLE: Ambari -->
<!-- SUBTITLE: A quick summary of Ambari -->

# Installation
* Ubuntu 18.04는 아직 지원 안함. (https://supportmatrix.hortonworks.com)


## Build Ambari 2.7.3

### Direct Building

#### Build
```wget http://www.apache.org/dist/ambari/ambari-2.7.3/apache-ambari-2.7.3-src.tar.gz (use the suggested mirror from above)
tar xfvz apache-ambari-2.7.3-src.tar.gz
cd apache-ambari-2.7.3-src
mvn versions:set -DnewVersion=2.7.3.0.0
 
pushd ambari-metrics
mvn versions:set -DnewVersion=2.7.3.0.0
popd
```

Ubuntu/Devian
```
mvn -B clean install jdeb:jdeb -DnewVersion=2.7.3.0.0 -DbuildNumber=4295bb16c439cbc8fb0e7362f19768dde1477868 -DskipTests -Dpython.ver="python >= 2.6"
```

#### Install Ambari Server
```
apt-get install ./ambari-server*.deb   #This should also pull in postgres packages as well.
```

### Repository
```
wget -O /etc/apt/sources.list.d/ambari.list http://public-repo-1.hortonworks.com/ambari/ubuntu16/2.x/updates/2.6.2.2/ambari.list
apt-key adv --recv-keys --keyserver keyserver.ubuntu.com B9733A7A07513CAD
apt-get update
apt-get install ambari-server
```



## Setup & Start Ambari Server

`ambari-server setup`
`ambari-server start`

## Install and Start Ambari Agent on All Hosts
```
sudo apt-get install ambari-agent
sudo vi /etc/ambari-agent/conf/ambari-agent.ini

sudo python /usr/lib/ambari-agent/lib/ambari_agent/HostCleanup.py --skip=users
```


## MySQL
파일 이름을 mysql-connector-java.jar 로 바꾸어서 할 것.
그렇지 않으면, `/var/lib/ambari-server/resources`에서 심볼릭 링크라도 걸어주자..
```
wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java_8.0.13-1ubuntu16.04_all.deb
dpkg -i mysql-connector-java_8.0.13-1ubuntu16.04_all.deb
ambari-server setup --jdbc-db=mysql --jdbc-driver=/usr/share/java/mysql-connector-java-8.0.13.jar
```

https://dev.mysql.com/downloads/connector/j/
- https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-8.0.13.tar.gz



# Setting
## Hostname
```
sudo vi /etc/hostname
sudo vi /etc/hosts
```

## Time Setting
```
sudo apt install ntp
```

## SSH Key Generation
1. `ssh-keygen`를 통해 .ssh에 `id_rsa.pub`과 `id_rsa`를 생성.
```
ssh-keygen
```
- `id_rsa`는 private key로 절대 노출되면 안됨.
- `id_rsa.pub`은 public key로 이것을 이용하여 인증함.


2. 접근 권한을 설정함.
```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_rsa
chmod 600 ~/.ssh/id_rsa.pub
chmod 600 ~/.ssh/authorized_keys
```

3. `id_rsa.pub`을 리모트 서버로 복사하고 `$HOME/.ssh/authorized_keys` 를 생성함. 또는 그 다음 줄에 추가. (복사 굳이 필요 없음)
```
cat $HOME/id_rsa.pub >> $HOME/.ssh/authorized_keys
```

4. `known_hosts`에 주소를 추가하기 위해 접속을 시도함.
```
ssh {HOST}
```

# master




# References
- https://cwiki.apache.org/confluence/display/AMBARI/Installation+Guide+for+Ambari+2.7.3