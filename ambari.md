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
# master




# References
- https://cwiki.apache.org/confluence/display/AMBARI/Installation+Guide+for+Ambari+2.7.3