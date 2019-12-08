FROM ruby:2.6.5-alpine3.10

ENV TZ Asia/Tokyo
ENV LANG C.UTF-8
ENV HOME /home/appuser
ENV APP_DIR ${HOME}/works

RUN apk add --no-cache nodejs yarn tzdata curl-dev make gcc libc-dev g++
# RUN apk add --no-cache sqlite-dev
RUN apk add --no-cache postgresql-dev
RUN gem install bundler

RUN mkdir -p ${APP_DIR}

ADD Gemfile ${APP_DIR}/
ADD Gemfile.lock ${APP_DIR}/
ADD package.json ${APP_DIR}/
ADD yarn.lock ${APP_DIR}/

WORKDIR ${APP_DIR}
RUN bundle install --jobs 4 --retry 5
RUN yarn install

RUN rm -rf /usr/local/bundle/cache/* /usr/local/share/.cache/* /var/cache/* /tmp/*
