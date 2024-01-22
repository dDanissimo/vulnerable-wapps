This subfolder contains tasks tasks that are being implemented at a cybersecurity elective course at the FoE of Lomonosov MSU.

Same tasks can be found at the following resource (with the whole project alongside them): https://github.com/dDanissimo/emsch-CTFd/tree/master/tasks

Example docker-compose config for all of the tasks (partial):
```
...

  web1:
    build:
      context: ./tasks/test_web
      dockerfile: Dockerfile
    restart: always
    volumes:
      - ./tasks/test_web:/app
    ports:
      - "0.0.0.0:5000:5000"
    depends_on:
      - db
      - cache
  web2:
    build:
      context: ./tasks/test_web2
      dockerfile: Dockerfile
    restart: always
    volumes:
      - ./tasks/test_web2:/app
    ports:
      - "0.0.0.0:5001:5001"
    depends_on:
      - db
      - cache
  web3:
    build:
      context: ./tasks/test_web3
      dockerfile: Dockerfile
    restart: always
    volumes:
      - ./tasks/test_web3:/app
    ports:
      - "0.0.0.0:5002:5002"
    depends_on:
      - db
      - cache

...
```

Full config can be found at: https://github.com/dDanissimo/emsch-CTFd/blob/master/docker-compose.yml
