FROM nextcloud:apache

RUN set -ex; \
    \
    apt-get update; \
    apt-get upgrade -y --no-install-recommends; \
    apt-get install -y --no-install-recommends \
        ffmpeg \
        imagemagick \
        ghostscript \
        libmagickcore-6.q16-6-extra \
        procps \
        smbclient \
        supervisor \
        libreoffice \
        libbz2-dev \
    ; \
    docker-php-ext-install bz2 \
    rm -rf /var/lib/apt/lists/*

# PDF preview
RUN sed -i 's/\(^ *<policy.*rights="\)\([^"]*\)\(".*PDF.*\/>\)/\1read|write\3/1' /etc/ImageMagick-6/policy.xml
