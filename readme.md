# Qt

The UNOFFICAL Qt docker image.

## What is Qt
Qt is much more than just a cross-platform SDK - it's a technology strategy that lets you quickly and cost-effectively design, develop, deploy, and maintain software while delivering a seamless user experience across all devices.

## How to use this image

### Create a Dockerfile in your Qt project

```dockerfile
# specify the node base image with your desired version node:<version>
FROM yeliex/qt
# replace this with your application's default port
EXPOSE 3000
```

You can then build and run the Docker image:

```bash
$ docker build -t my-nodejs-app .
$ docker run -it --rm --name my-running-app my-qt-app
```

If you prefer Docker Compose:

```yaml
version: "2"
services:
  service:
    image: "yeliex/qt"
    working_dir: "/data"
    volumes:
      - ./:/data
    expose:
      - 3000
    command: "./run" # anything to start your app
```

You can then run using Docker Compose:

```bash
$ docker-compose up -d
```
