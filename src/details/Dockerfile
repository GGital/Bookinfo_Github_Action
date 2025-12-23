FROM ruby:2.7-alpine

RUN apk add --no-cache build-base

WORKDIR /app

COPY Gemfile ./

RUN bundle config set --local path 'vendor/bundle' && \
    bundle config set --local system 'false' && \ 
    bundle install


COPY details.rb ./

EXPOSE 9080

CMD ["bundle", "exec", "ruby", "details.rb", "9080"]