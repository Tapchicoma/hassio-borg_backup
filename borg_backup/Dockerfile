ARG BUILD_FROM
FROM $BUILD_FROM
ENV LANG C.UTF-8

RUN apk add --no-cache --update \
          borgbackup \
          openssh-client \
          openssh-keygen \
          jq

WORKDIR /

RUN ssh-keygen -q -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "hassio"

COPY start.sh /app/start.sh
RUN chmod a+x /app/start.sh
CMD ["/app/start.sh"]
