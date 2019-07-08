# AWS Fargate Sample
Nginx <=> uWSGI <=> Flask

## AWS Profile
```
$ export AWS_DEFAULT_PROFILE=[aws profile name]
```

## Nginx 
```
$ cd nginx
$ docker build -t nginx .
$ docker tag nginx:latest [0-9].dkr.ecr.ap-northeast-1.amazonaws.com/nginx:latest
```

## uWSGI + Flask
```
$ cd uwsgi
$ docker build -t uwsgi .
$ docker tag uwsgi:latest [0-9].dkr.ecr.ap-northeast-1.amazonaws.com/uwsgi:latest
```

## Docker Run
```
$ docker run -p 3031:3031 uwsgi
```
