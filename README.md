# DevOps Assessment

## Running tests

You can run the tests of all apps by using `make test`

## Building

First you need to ensure that the common libraries are installed: run `make libs` to install them to your local `~/.m2` repository. This will allow you to build the JARs.

To build all the JARs and generate the static tarball, run the `make clean all` command from this directory. The JARs and tarball will appear in the `build/` directory.

## Running

All the apps take environment variables to configure them

### Static assets

`cd` to `front-end/public` and run `./serve.py` (you need Python3 installed). This will serve the assets on port 8000.

### Front-end app

`java -jar build/front-end.jar`

*Environment variables*:

* `APP_PORT`: The port on which to run the app
* `STATIC_URL`: The URL on which to find the static assets (should be `http://localhost:8000` if you're using the `serve.py` app referenced above)
* `QUOTE_SERVICE_URL`: The URL on which to find the quote service

### Quote service

`java -jar build/quotes.jar`

*Environment variables*

* `APP_PORT`: The port on which to run the app