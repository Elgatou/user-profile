# Профиль пользователя

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

## run application in docker container

```bash
# create image based on dockerfile
$ docker build -t nuxt-test/user-profile .

# run docker container on port 3000
$ docker run -p 3000:3000 nuxt-test/user-profile
```
