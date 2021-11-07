# 실습 환경 구성

## ElasticSearch

```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.15.1
```

## Kibana

```
docker pull docker.elastic.co/kibana/kibana:7.15.1
```

## FileBeat

```
docker pull docker.elastic.co/beats/filebeat:7.15.1
```

## Logstash

```
docker pull docker.elastic.co/logstash/logstash:7.15.1
```

## 네트워크 생성

```
docker network create elastic
```

## ElasticSearch 싱글 노드 실행

```
docker run -d --name es01-test --net elastic -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.15.1
```

## Logstash 실행

```
docker run -d --name ls01-test --net elastic -p 5044:5044 -v /logstash.conf:/usr/share/logstash/pipeline/logstash.conf docker.elastic.co/logstash/logstash:7.15.1
```

## Kibana 실행

```
docker run -d --name kib01-test --net elastic -p 5601:5601 -e "ELASTICSEARCH_HOSTS=http://es01-test:9200" docker.elastic.co/kibana/kibana:7.15.1
```

## Filebeat 실행

```
docker run -d --name fb01-test --net elastic -v /test.log:/usr/share/filebeat/logs/access_log filebeat:latest
```