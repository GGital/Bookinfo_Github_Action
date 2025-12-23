FROM ruby:2.7-alpine

ENV GEM_HOME="/app/vendor/bundle"
ENV PATH="$GEM_HOME/bin:$PATH"
ENV BUNDLE_SILENCE_ROOT_WARNING=1

RUN apk add --no-cache build-base

WORKDIR /app

COPY Gemfile ./

RUN bundle config set --local path 'vendor/bundle' && \
    bundle config set --local system 'false' && \ 
    bundle install


COPY details.rb ./

EXPOSE 9080

CMD ["bundle", "exec", "ruby", "details.rb", "9080"]