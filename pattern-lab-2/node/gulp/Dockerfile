FROM node:4-onbuild
MAINTAINER George White <stonehippo@gmail.com>

# create a non-priveleged user
RUN groupadd -r pl2 \
    && useradd -r -g pl2 pl2 \
    && mkdir /home/pl2 \
    && chown pl2 /home/pl2 \
    && chgrp pl2 /home/pl2

RUN apt-get update \
    && apt-get install -y git

RUN chmod o+w /opt

USER pl2

WORKDIR /opt

RUN git clone https://github.com/pattern-lab/edition-node-gulp.git \
    /opt/pattern-lab

WORKDIR /opt/pattern-lab
RUN npm install \
    && npm install gulp

CMD ["./node_modules/.bin/gulp", "patternlab:serve"]

VOLUME /opt/pattern-lab/source

EXPOSE 3000
