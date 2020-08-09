ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

COPY src/* /src/

RUN apk add python2
RUN apk add openssh

CMD /usr/bin/python2 /src/sshreachme.py
