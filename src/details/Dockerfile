FROM ruby:2.7-slim

WORKDIR /app

COPY Gemfile ./

RUN bundle install

COPY details.rb ./

EXPOSE 9080

CMD ["ruby", "details.rb", "9080"]
