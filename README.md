Jekyll-livereload
===

Ready-to-go docker environment for Jekyll livereload.

## How to use
- Put your jekyll source files into `/source` (or edit the volumes in `docker-compose.yml` file).
- Build and launch docker-compose :


    docker-compose build
    docker-compose up -d

- open your browser at [http://localhost:8008](http://localhost:8008) ;

- modify a file in your watched directory ;

- Magic, the page is refreshed ! :o


## What's under the hood ?

### [`cethy/alpine-jekyll:v1.0`](https://github.com/Cethy/alpine-jekyll/)
Docker image (21Mo) which watch for modification into the `/source` directory and run jekyll when modified.

### [`cethy/apline-nginx-livereload-injection:v1.0`](https://github.com/Cethy/apline-nginx-livereload-injection/)
Docker image (7Mo) which act as a reverse proxy for `_site` and inject the livereload js snippet.

### [`cethy/alpine-livereload:v1.0`](https://github.com/Cethy/alpine-livereload)
Docker image (16Mo) which watch for modification into the `/_site` directory and reload the page in the navigator.
