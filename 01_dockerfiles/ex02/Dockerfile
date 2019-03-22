FROM ruby
RUN apt-get update -y && apt-get upgrade -y
RUN gem install rails
RUN mkdir /opt/app
ONBUILD COPY . /app/opt
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rail db:migrate
ONBUILD RUN rail db:seed

# https://runnable.com/docker/rails/dockerize-your-ruby-on-rails-application
# https://stackoverflow.com/questions/10301794/difference-between-rake-dbmigrate-dbreset-and-dbschemaload
# ONBUILD : https://www.learnitguide.net/2018/06/docker-onbuild-command-with-examples.html
