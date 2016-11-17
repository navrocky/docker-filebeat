# Filebeat Docker image based on Alpine Linux

[Filebeat](https://www.elastic.co/products/beats/filebeat) is a lightweight shipper for logs.
  
## Simple usage

```
$ docker run --rm -v ${PWD}/filebeat.yml:/filebeat.yml navrocky/filebeat:latest 
```

**filebeat.yml** content is:
```
filebeat.prospectors:
- input_type: log
  paths:
    - /my_service/logs/info.log

output.logstash:
  hosts: ["logstashhost:5043"]
```