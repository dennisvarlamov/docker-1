FROM ruby

ONBUILD RUN apt-get update && apt-get -y upgrade && apt-get install -y buil-essential libpq-dev nodejs sqlite3 /bin/sh

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed