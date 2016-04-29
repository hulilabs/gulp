# Introduction
This repo contains Gulp, a dockerized service to run Gulp tasks.

![Gulp](https://avatars2.githubusercontent.com/u/6200624?v=3&s=200)

Gulp let's us automate tasks when building web applications. For example, we run tasks to compress our web files (images, js, css) to serve them more efficiently, also we run tasks to check the code format (jshint), or we can also run watchers to execute tasks when files are modified. If you are new to Gulp we recommend you to check the [official documentation](https://github.com/gulpjs/gulp/blob/master/docs/README.md) first.

# Getting started

## Requirements
- [Docker](https://docs.docker.com/engine/installation/)

## Configuration
Check the [API docs ](https://github.com/gulpjs/gulp/blob/master/docs/API.md) section of the Gulp official documentation as a guideline for configuring your tasks.

## Usage
This service is meant to start a docker container, run a gulp task and then be removed when the task is completed. For example:
```
docker run -it --rm -v $(pwd):/srv -w="/srv/src/resource" huli/gulp build
```

The above comand will start a docker container with the `huli/gulp` image, mounting the folder project in the `/srv` folder and setting `/srv/src/resource` as the working directory, this should be the folder where the `Gruntfile.js` is located. Finally it will run npm install and execute the `build` task.
