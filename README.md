# Getting Started with Docker Volume

## docker-compose.yml

```docker-compose
version: "3"
services:
  web:
    build:
      context: .
      dockerfile: Dockerfile.dev
    ports:
      - "3000:3000"
    volumes:
      - /app/node_modules
      - .:/app
  tests:
    build:
      context: .
      dockerfile: Dockerfile.dev
    volumes:
      - /app/node_modules
      - .:/app
    command: ["npm", "run", "test"]
```

### `docker-compose build`

Build the compose file

### `docker-compose up`

Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

On change file in the local directory, changes in the browser can be seen immediately