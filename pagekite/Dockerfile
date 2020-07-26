ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

COPY src/* /src/

RUN apk add python2 \
  && curl -s -o /src/pagekite.py "https://pagekite.net/pk/pagekite.py"

CMD /usr/bin/python2 /src/pagekite-with-options.py
