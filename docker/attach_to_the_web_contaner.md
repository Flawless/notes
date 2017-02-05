Docker-compose start detached service and attach to web container
```bash
docker-compose up -d                                                                                      
docker attach myapp_web_1 # OR docker attach --sig-proxy=false myapp_web_1 for stop with C+c
```