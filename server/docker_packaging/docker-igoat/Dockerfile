FROM ruby:3.1

RUN mkdir -p /usr/src/app

ENV RACK_ENV production

RUN git clone https://github.com/qwezxcdegen/iGoat-Swift.git /tmp/

RUN mv /tmp/server/* /usr/src/app/

COPY Gemfile /usr/src/app/

ADD startup.sh /

WORKDIR /usr/src/app

EXPOSE 8080

RUN gem install sinatra webrick rack

RUN gem install bundler && bundle install --jobs 4 --retry 3

CMD ["/bin/bash", "/startup.sh"]
