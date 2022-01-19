FROM httpd

ARG webPublicHost
ARG nextcloudPublicHost

COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY httpd-ssl.conf /usr/local/apache2/conf/extra/httpd-ssl.conf
COPY web.conf /usr/local/apache2/conf/extra/web.conf
COPY nextcloud.conf /usr/local/apache2/conf/extra/nextcloud.conf

RUN sed -i \
    -e "s/WEB_PUBLIC_HOST/$webPublicHost/g" \
    -e "s/NEXTCLOUD_PUBLIC_HOST/$nextcloudPublicHost/g" \
    /usr/local/apache2/conf/httpd.conf

RUN sed -i \
    -e "s/WEB_PUBLIC_HOST/$webPublicHost/g" \
    /usr/local/apache2/conf/extra/web.conf

RUN sed -i \
    -e "s/NEXTCLOUD_PUBLIC_HOST/$nextcloudPublicHost/g" \
    /usr/local/apache2/conf/extra/nextcloud.conf