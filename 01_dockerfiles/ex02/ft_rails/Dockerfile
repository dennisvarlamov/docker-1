FROM ruby

ONBUILD RUN apt-get update && apt-get -y upgrade && apt-get install -y buil-essential libpq-dev nodejs sqlite3 /bin/sh

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# How to build it?
# docker build -t ft-rails:on-build .

#docker build -t ft-rails:on-build . — Build an image from your Dockerfile
#docker build -t ex02 . — Build an image from Dockerfile provided by task
#docker run -it --rm -p 3000:3000 ex02 — Run created image