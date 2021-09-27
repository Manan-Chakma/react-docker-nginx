# Getting Started with Docker Nginx and React App

## Dockerfile

```Dockerfile
FROM node:alpine as builder
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .

RUN npm run build

FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html 
```

### `docker build .`

Runs the app in the development mode.\


The page will reload if you make edits.\
You will also see any lint errors in the console.

### `docker run -p 8080:80 <image-id>`

Open [http://localhost:8080](http://localhost:3000) to view it in the browser.