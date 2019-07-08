FROM python:3.7-alpine

ENV PYTHONUNBUFFERED 1
RUN mkdir -p /var/www/app
WORKDIR /var/www
COPY ./requirements.txt ./
COPY ./uwsgi.ini ./
RUN apk update && \
    apk upgrade --update && \
    apk add --no-cache gcc g++ make python3-dev build-base libffi-dev jpeg-dev zlib-dev freetype-dev lcms2-dev \
        openjpeg-dev tiff-dev tk-dev tcl-dev harfbuzz-dev fribidi-dev && \
    rm -rf /var/cache/apk/* && \
    pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt
WORKDIR /var/www/app
COPY ./app /var/www/app
CMD ["uwsgi","--ini","/var/www/uwsgi.ini"]
