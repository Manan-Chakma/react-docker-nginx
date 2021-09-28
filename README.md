# Getting Started with Travis CI Docker Nginx and React App

## .travis.yml
```
# super user permission
sudo: required

services:
  - docker

before_install:
  - docker build -t manan/docker-react -f Dockerfile.dev .

# contain list of commands need to executed to run the test suite
script:
  - docker run -e CI=true manan/docker-react npm run test
```
### `Steps`

1. Sync Project Directory in Travis CI
2. Create and Edit the .travis.yml file
3. Push Code in Github

### `Result`

After Completiion:

![Image of Travis CI Dashboard](https://github.com/Manan-Chakma/react-docker-nginx/blob/master/public/travisci.png)