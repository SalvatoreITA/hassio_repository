ARG BUILD_FROM
FROM $BUILD_FROM
RUN mkdir /dynu_reverse_proxy

WORKDIR /dynu_reverse_proxy

RUN apk add --no-cache \
        python3 \
        py3-pip \
        openssl \
        nginx \
        certbot \
        certbot-nginx
COPY run.sh /dynu_reverse_proxy
COPY data/nginx.conf* /etc/nginx/
COPY data/check_cert.py /dynu_reverse_proxy/

RUN chmod a+x /dynu_reverse_proxy/run.sh

RUN pip3 install noipy

CMD [ "/dynu_reverse_proxy/run.sh" ]
