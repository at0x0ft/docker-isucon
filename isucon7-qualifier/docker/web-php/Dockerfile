FROM alpine AS build-dev

ARG GIT_URL=https://github.com/at0x0ft/isucon7-qualify.git

RUN \
  apk --no-cache add git && \
  git clone --depth=1 $GIT_URL /isubata && \
  rm -rf /isubata/.git

FROM nginx:1.10

COPY --from=build-dev /isubata /home/isucon/isubata
#COPY --from=build-dev /isubata/files/app/nginx.php.conf /etc/nginx/conf.d/isucon.php.conf
COPY isucon.php.conf /etc/nginx/conf.d/isucon.php.conf
