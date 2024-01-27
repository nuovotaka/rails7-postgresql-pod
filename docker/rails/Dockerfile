FROM ruby:3.2.1

RUN apt-get update -qq && apt-get install -y postgresql-client
RUN mkdir /myapp
WORKDIR /myapp
ENV RAILS_LOG_TO_STDOUT="1" \
  RAILS_ENV="development"
COPY Gemfile /myapp/Gemfile
COPY Gemfile.lock /myapp/Gemfile.lock
RUN bundle install
COPY . /myapp

COPY docker/rails/entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]

