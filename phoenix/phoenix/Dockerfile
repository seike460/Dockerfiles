FROM elixir:latest
MAINTAINER seike460

ENV NODE_VERSION 10.x
ENV NPM_VERSION 6.3.x

RUN curl -sL https://deb.nodesource.com/setup_${NODE_VERSION} | bash \
  && apt-get install -y nodejs

RUN npm install npm@${NPM_VERSION} -g

RUN mix local.hex --force && \
  mix archive.install --force https://github.com/phoenixframework/archives/raw/master/phx_new.ez && \
  mix local.rebar --force

RUN apt-get install -y inotify-tools

WORKDIR /app
