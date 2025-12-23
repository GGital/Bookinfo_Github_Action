FROM ruby:2.7-alpine

WORKDIR /app

RUN mkdir -p /usr/local/bundle && chmod 777 /usr/local/bundle

COPY Gemfile ./

RUN bundle install

COPY details.rb ./

EXPOSE 9080

CMD ["ruby", "details.rb", "9080"]
