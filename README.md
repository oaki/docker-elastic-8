How to start

1. >docker-compose up -d

2. go to kibana http://localhost:5601/

3. reset user
    find name(id) of container docker ps

    >docker exec -it d0ffa3755705 /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic

4. copy password ****
5. Copy the http_ca.crt security certificate from your Docker container to your local machine.
   
    >docker cp d0ffa3755705:/usr/share/elasticsearch/config/certs/http_ca.crt .
   
6. add certificate into osx with double click
7. Open a new terminal and verify that you can connect to your Elasticsearch
    >curl --cacert http_ca.crt -u elastic https://localhost:9200
8. create token for kibana
   >docker exec -it d0ffa3755705 /usr/share/elasticsearch/bin/elasticsearch-create-enrollment-token -s kibana
9. copy token and put it inside kibana web
10. get kibana passcode
   >docker exec -it b6df95b2a5c6 bin/kibana-verification-code
11. login
    1. username elastic
    2. password ****



