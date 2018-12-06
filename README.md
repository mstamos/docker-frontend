# Run tests via exec command

First we build and run our docker
In this example we use docker-compose without the section of tests because we
don't wont to display test suite into docker-compose out put. We want them in separate
window

```
// docker-compose.yml
version: '3'
services:
  web:
    build:
      context: .
      dockerfile: Dockerfile.dev
    ports:
      - '3000:3000'
    volumes:
      - app/node_modules
      - .:/app
```

```
docker-compose up
docker ps // To get the container id and then
docker exec -it <container-id> npm run test
```
