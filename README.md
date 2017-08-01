# lightweight-php
Lightweight php CLI based on alpine with frequents modules used by BiiG.

This image only contains the php CLI interpreter.

## Create a Dockerfile in your PHP project
```
FROM biig/lightweight-php:latest
COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
CMD [ "php", "./your-script.php" ]
```

Then, run the commands to build and run the Docker image:
```
$ docker build -t my-php-app .
$ docker run -it --rm --name my-running-app my-php-app
```

## Run a single PHP script

```$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp biig/lightweight-php:latest php your-script.php```


## Attach a volume and spawn a new shell

```$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp biig/lightweight-php:latest sh```

