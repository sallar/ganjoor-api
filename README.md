# Ganjoor API
[![CircleCI](https://circleci.com/gh/ganjoor/ganjoor-api.svg?style=svg)](https://circleci.com/gh/ganjoor/ganjoor-api)

## Local Development

Rename or copy `.env.example` to `.env` and set needed variables in it.

Then:

``` bash
$ yarn
$ yarn dev
```

## Development Docker

If you just want to run a docker container locally to host the API and the Database for you:

``` bash
$ yarn
$ yarn build
$ docker-compose up
```

You'll see a bunch of errors at first, because it takes a bit of time for the MySQL container to start up (due to the large db dump file). As soon as it has started up, the API container will connect to it and you'll see the message:

    Server started at port 4003

At that point you can head to [http://localhost:4003/](http://localhost:4003/) to checkout the API. You can also make the containers run in the background by cancelling the current process and running:

``` bash
$ docker-compose up -d
```

## Production Docker

``` bash
$ docker build ganjoor-api .
$ docker run ganjoor-api --env AUTH0_DOMAIN=... --env AUTH0_CLIENT_ID=... --env AUTH0_CLIENT_SECRET=...
```

## API Documentation

Head to [http://localhost:4003/api-docs](http://localhost:4003/api-docs) to read the API documentation.

## Sponsors

![](http://cdn.auth0.com/oss/badges/a0-badge-dark.png)


## License

This software is released under the [MIT License](LICENSE).
