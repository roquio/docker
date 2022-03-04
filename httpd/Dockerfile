FROM httpd

ARG WEB_PUBLIC_HOST
ARG NEXTCLOUD_PUBLIC_HOST
ARG COLLABORA_PUBLIC_HOST


COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY httpd-ssl.conf /usr/local/apache2/conf/extra/httpd-ssl.conf
COPY web.conf /usr/local/apache2/conf/extra/web.conf
COPY nextcloud.conf /usr/local/apache2/conf/extra/nextcloud.conf
COPY collabora.conf /usr/local/apache2/conf/extra/collabora.conf


RUN sed -i \
    -e "s/WEB_PUBLIC_HOST/$WEB_PUBLIC_HOST/g" \
    /usr/local/apache2/conf/httpd.conf

RUN sed -i \
    -e "s/WEB_PUBLIC_HOST/$WEB_PUBLIC_HOST/g" \
    /usr/local/apache2/conf/extra/web.conf

RUN sed -i \
    -e "s/NEXTCLOUD_PUBLIC_HOST/$NEXTCLOUD_PUBLIC_HOST/g" \
    /usr/local/apache2/conf/extra/nextcloud.conf

RUN sed -i \
    -e "s/COLLABORA_PUBLIC_HOST/$COLLABORA_PUBLIC_HOST/g" \
    /usr/local/apache2/conf/extra/collabora.conf
