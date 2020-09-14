# Fearless Tracker

This project is a simple counter app. The app makes api calls to 
get the current hit count from an api.

Another api is called to retrieve a random fact about the number returned 
by the first api.

The project was written in `Vue` and defaults to port 3000.

The port can be set in `package.json`.

## Project setup

The project requires `Vue` and `axios`. The following commands can be 
used to set up the required environment.

```
npm install
npm install -g @vue/cli
npm install axios
```

Alternatively, the Dockerfile can be used to build and run the container. 



### Compiles and hot-reloads for development

To run manually:
```
npm run serve
```

To run in Docker:
```
docker run tracker
```

### Compiles and minifies for production

To build manually:
```
npm run build
```

To build in Docker:
```
docker build -t fearless_tracker .
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
