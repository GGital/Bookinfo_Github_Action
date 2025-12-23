FROM ruby:2.7-alpine

ENV HOME=/tmp

WORKDIR /app

RUN apk add --no-cache build-base

COPY Gemfile ./

RUN mkdir -p vendor/bundle && \
    bundle config set --local path 'vendor/bundle' && \
    bundle install --retry 3

COPY details.rb ./

EXPOSE 9080

CMD ["bundle", "exec", "ruby", "details.rb", "9080"]