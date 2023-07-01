This is a fork of the searxng/searxng-docker repo, with the Caddy container removed. It makes Searxng available on localhost:8001 for use behind a reverse proxy. 
1. Clone the repo
2. ```cd searxng-docker```
3. ```sed -i "s|ultrasecretkey|$(openssl rand -hex 32)|g" searxng/settings.yml```
4. ```docker compose up -d```
