FROM ruby:2.2.5
RUN apt-get update

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get dist-upgrade -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" --force-yes

RUN apt-get -y --force-yes install sudo

#RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o -y /usr/share/keyrings/debian-archive-keyring.gpg


#RUN sudo apt-get update
#RUN deb http://ftp.de.debian.org/debian jessie main


RUN apt-get install -y --force-yes \
    build-essential \
    libpq-dev \
    libsqlite3-dev \
    libsasl2-dev \
    mysql-client \
    curl \
    ca-certificates \
    net-tools \
    vim

# install nodejs
RUN mkdir /workspace
WORKDIR /workspace
##
RUN curl -cL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
RUN cat nodesource_setup.sh
#
RUN bash nodesource_setup.sh
RUN apt-get install -y --force-yes nodejs
RUN rm -rf /workspace

## install nokogiri
#RUN apt-get install -y --force-yes libxml2-dev libxslt1-dev

## install snappy
#RUN apt-get install -y --force-yes snappy

## git config for using https:// instead of git://
#RUN git config --global url."https://github".insteadOf git://github

## install bundler
#RUN gem install bundler -v '1.17.3'

## install rmagick
#RUN apt-get install -y --force-yes imagemagick libmagickwand-dev
#RUN gem install rmagick -v 2.13.4

## install rails
#RUN gem install rails -v 4.1.12
#
## install specific_install
#RUN gem install specific_install
#
## bundle 설치 중 문제가 발생하는 package는 기본 설치
## mimemagic 0.3.2
#RUN gem specific_install https://github.com/mimemagicrb/mimemagic --ref=3543363026121ee28d98dfce4cb6366980c055ee
#
#RUN mkdir -p /jobplanet_app
#WORKDIR /jobplanet_app
#
## Copy the Gemfile as well as the Gemfile.lock and install
## the RubyGems. This is a separate step so the dependencies
## will be cached unless changes to one of those two files
## are made.mimemagic
#COPY Gemfile Gemfile.lock ./
##RUN bundle config github.https true
#RUN bundle install --jobs "$(nproc)" --retry 5
##RUN rm Gemfile Gemfile.lock
#
## run npm install
#
#RUN mkdir -p /jobplanet_app/client
#WORKDIR /jobplanet_app/client
#COPY client/package.json package.json
#RUN npm config set registry https://registry.npmjs.org
#RUN npm install --global
#RUN npm install --global yarn
#
## RUN yarn global add webpack webpack-cli
## RUN npm install -g webpack webpack-cli
#
## set workdir
#WORKDIR /jobplanet_app
##RUN rm Gemfile Gemfile.lock
#
