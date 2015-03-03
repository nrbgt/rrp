FROM dockerfile/nodejs
WORKDIR /srv/app/

ADD package.json /srv/app/
RUN npm install .

ADD ["./bower.json", "./.bowerrc", "/srv/app/"]
RUN ./node_modules/.bin/bower install --allow-root

ADD ./bin /srv/app/bin

VOLUME ["/srv/app/src"]

EXPOSE 8080

CMD ["npm", "start"]
