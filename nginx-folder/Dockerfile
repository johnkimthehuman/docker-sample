FROM nginx:latest

RUN apt-get update \
  && apt-get install -y vim \
  && apt-get install -y nano

COPY index.html /usr/share/nginx/html/index.html
COPY background.png /usr/share/nginx/html/background.png
