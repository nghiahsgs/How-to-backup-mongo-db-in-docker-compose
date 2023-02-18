# How-to-backup-mongo-db-in-docker-compose
How to backup mongo db in docker-compose


Let's say that I have a docker-compose file like this, which will initialize a mongo db. And I want to backup its volume regularly.
```
version: '3'
services:
  mongo:
    image: mongo
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: pass
    ports:
      - "27017:27017"
    volumes:
      - /root/test_mongo_volume/volume_2:/data/db

```


Run docker-compose
```
docker-comose -f docker-compose.yaml up
```

After the docker compose start successfully, the connection string for mongo db
```
mongodb://root:pass@localhost:27017/
```

Now the data of mongo will auto mapping to '/root/test_mongo_volume/volume_2'

You can backup the folder regulary or move it to other server. And run the docker-compose same like above. It's the way to backup dabase mongo db was build from docker-compose
