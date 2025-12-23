FROM ruby:2.7-alpine

USER root

WORKDIR /app

COPY Gemfile ./

ENV BUNDLE_PATH='/app/vendor/bundle'

RUN bundle install

COPY details.rb ./

EXPOSE 9080

CMD ["ruby", "details.rb", "9080"]
