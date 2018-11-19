<!-- TITLE: Ambari -->
<!-- SUBTITLE: A quick summary of Ambari -->

# Installation
## Build Ambari 2.7.3
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

## Install Ambari Server
```
apt-get install ./ambari-server*.deb   #This should also pull in postgres packages as well.
```

## Setup & Start Ambari Server

`ambari-server setup`
`ambari-server start`

## Install and Start Ambari Agent on All Hosts


# Setting
## SSH Key Generation
1. `ssh-keygen`를 통해 .ssh에 `id_rsa.pub`과 `id_rsa`를 생성.
- `id_rsa`는 private key로 절대 노출되면 안됨.
- `id_rsa.pub`은 public key로 이것을 이용하여 인증함.
2. 접근 권한을 설정함.
```
chmod 700 ~/.ssh
chmod 644 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```
3. `id_rsa.pub`을 리모트 서버로 복사하고 `$HOME/.ssh/authorized_keys` 를 생성함.
```
cat $HOME/id_rsa.pub >> $HOME/.ssh/authorized_keys
```

# master




# References
- https://cwiki.apache.org/confluence/display/AMBARI/Installation+Guide+for+Ambari+2.7.3