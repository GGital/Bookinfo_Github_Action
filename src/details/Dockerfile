FROM ruby:2.7-alpine

USER root

WORKDIR /app

COPY Gemfile ./

RUN bundle install

COPY details.rb ./

EXPOSE 9080

CMD ["ruby", "details.rb", "9080"]
