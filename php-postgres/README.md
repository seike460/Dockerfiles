### OS X

1: edit docker-compose.override.yml
```
$ vim docker-compose.override.yml
```

2. your projects clone to host's data-box volumes default (./php/app

```
git clone https://github.com/{$yourAccount}/{$yourApp} ./php/app
```

3: build images
```
$ docker-compose build 
```

4: Start services
```
$ docker-compose up -d
```
