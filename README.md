# rizzoma-docker
This is a docker image to run rizzoma standalone for testing or quick deploys.

## Description

This is a docker image to run rizzoma standalone for testing or quick deploys. It don't have sphinxsearch configured. An e-mail service (mailcatcher) is running on port 1080 and can be used to see all e-mails sent by the application. All configurations are default and this docker isn't hardened yet so I don't recommend use this image for long term deployment, just for tests or as disposable project. 

## Install

To spin up the latest version of this image just run:

```
docker run -p 8000:8000 -p 1080:1080 -t pimps/rizzoma
```

To build this docker image manually on your machine, just execute:

```
git clone https://github.com/pimps/rizzoma-docker.git
cd rizzoma-docker
docker build -t rizzoma .
docker run -p 8000:8000 -p 1080:1080 -t rizzoma
```

- Rizzoma will be running at http://localhost:8000/
- Mailcatcher will be running at http://localhost:1080/

## TODO

- FIXME: The building with sphinxsearch isn't working as expected using the default configuration files in the rizzoma building proccess. Create a docker composer to agregate a sphinxsearch instance and update configurations into settings.coffee.
- SECURITY IMPROVEMENT: Hardenize the docker image to run the daemons into the supervisord with low privilege user and also generate important secret infos from the settings.coffee file (like hardcoded keys and passwords) dinamically per build.

