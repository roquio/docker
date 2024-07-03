FROM httpd

ARG WEB_PUBLIC_HOST
ARG NEXTCLOUD_PUBLIC_HOST
ARG COLLABORA_PUBLIC_HOST
ARG DOCKER_REGISTRY_PUBLIC_HOST


COPY conf/httpd.conf /usr/local/apache2/conf/httpd.conf
COPY conf/httpd-ssl.conf /usr/local/apache2/conf/extra/httpd-ssl.conf
COPY conf/extra/web.conf /usr/local/apache2/conf/extra/web.conf
COPY conf/extra/nextcloud.conf /usr/local/apache2/conf/extra/nextcloud.conf
COPY conf/extra/collabora.conf /usr/local/apache2/conf/extra/collabora.conf
COPY conf/extra/docker-registry.conf /usr/local/apache2/conf/extra/docker-registry.conf


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

RUN sed -i \
    -e "s/DOCKER_REGISTRY_PUBLIC_HOST/$DOCKER_REGISTRY_PUBLIC_HOST/g" \
    /usr/local/apache2/conf/extra/docker-registry.conf
