FROM verdaccio/verdaccio:4

USER root

ENV NODE_ENV=production

RUN npm i && npm install verdaccio-aws-s3-storage

COPY .htpasswd /verdaccio/conf/.htpasswd
COPY config.yaml /verdaccio/conf/config.yaml

USER verdaccio

CMD $VERDACCIO_APPDIR/bin/verdaccio --config /verdaccio/conf/config.yaml --listen $VERDACCIO_PROTOCOL://0.0.0.0:$VERDACCIO_PORT