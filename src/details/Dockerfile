FROM ruby:2.7-alpine

WORKDIR /app

RUN mkdir -p /app/tmp /app/vendor/bundle /app/bundle_config
ENV HOME=/app
ENV TMPDIR=/app/tmp
ENV BUNDLE_APP_CONFIG=/app/bundle_config
ENV GEM_HOME=/app/vendor/bundle
ENV PATH="$GEM_HOME/bin:$PATH"

RUN chmod -R 777 /app

RUN apk add --no-cache build-base

COPY Gemfile ./

RUN bundle config set --local path '/app/vendor/bundle' && \
    bundle install --retry 3

COPY details.rb ./

EXPOSE 9080

CMD ["bundle", "exec", "ruby", "details.rb", "9080"]