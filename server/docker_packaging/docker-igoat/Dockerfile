FROM ruby:2.4

RUN mkdir -p /usr/src/app

ENV RACK_ENV production

RUN git clone https://github.com/qwezxcdegen/iGoat-Swift.git /tmp/

RUN mv /tmp/server/* /usr/src/app/

COPY Gemfile /usr/src/app/

ADD startup.sh /

WORKDIR /usr/src/app

EXPOSE 8080

RUN gem install bundler -v 1.16.1

RUN bundle install

CMD ["/bin/bash", "/startup.sh"]
