ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN apk add python2 \
  && curl -s -o src/pagekite.py "https://pagekite.net/pk/pagekite.py"

COPY src/* /src/

CMD /usr/bin/python2 /src/pagekite-with-options.py
