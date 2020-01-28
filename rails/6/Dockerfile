FROM ruby:latest

# Append node source list and install Lib pq, nodejs, ghostscript, curl and yarn
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - \
  && apt-get update -qq \
  && apt-get install -y build-essential libpq-dev nodejs ghostscript \
  && npm install yarn -g \
  # The following are used to trim down the size of the image by removing unneeded data
  && apt-get clean autoclean \
  && apt-get autoremove -y \
  && rm -rf \
    /var/lib/apt \
    /var/lib/dpkg \
    /var/lib/cache \
    /var/lib/log


RUN gem install rails -v 6 \
  && gem install pg

RUN mkdir /app
WORKDIR /app

CMD [ "irb" ]
