This is a fork of the searxng/searxng-docker repo, with the Caddy container removed. It makes Searxng available on localhost:8001 for use behind a reverse proxy. 
1. Clone the repo
2. ```cd searxng-docker```
3. ```sed -i "s|ultrasecretkey|$(openssl rand -hex 32)|g" searxng/settings.yml```
4. ```docker compose up -d```
5. edit the server block to inlude ```proxy_set_header Host $host;
proxy_set_header Connection $http_connection;
proxy_set_header X-Forwarded-For $http_cf_connecting_ip;
proxy_set_header X-Real-IP $http_cf_connecting_ip;
proxy_set_header X-Scheme $scheme;```
This forwards the users' real IP to the instance, avoiding the "too many requests" issue.
