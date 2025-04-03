FROM ruby:3

RUN mkdir -p /usr/src/app

ENV RACK_ENV production

RUN git clone https://github.com/qwezxcdegen/iGoat-Swift.git /tmp/

RUN mv /tmp/server/* /usr/src/app/

ADD startup.sh /

WORKDIR /usr/src/app

EXPOSE 8080

RUN gem install sinatra webrick rack

CMD ["/bin/bash", "/startup.sh"]
