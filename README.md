# docker

## Build

    docker-compose build --pull

## Post-installation commands

### Nextcloud

    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set default_language --value "fr"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set default_locale --value "fr_FR"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set default_phone_region --value "FR"
    
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enable_previews --value true --type=boolean
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set preview_libreoffice_path --value "/usr/bin/libreoffice"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set preview_office_cl_parameters --value " --headless --nologo --nofirststartwizard --invisible --norestore --convert-to png --outdir "
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 0 --value "OC\Preview\PNG"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 1 --value "OC\Preview\JPEG"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 2 --value "OC\Preview\GIF"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 3 --value "OC\Preview\HEIC"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 4 --value "OC\Preview\BMP"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 5 --value "OC\Preview\XBitmap"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 6 --value "OC\Preview\MP3"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 7 --value "OC\Preview\TXT"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 8 --value "OC\Preview\MarkDown"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 9 --value "OC\Preview\OpenDocument"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 10 --value "OC\Preview\Krita"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 11 --value "OC\Preview\Illustrator"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 12 --value "OC\Preview\Movie"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 13 --value "OC\Preview\MSOffice2003"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 14 --value "OC\Preview\MSOffice2007"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 15 --value "OC\Preview\MSOfficeDoc"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 16 --value "OC\Preview\PDF"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 17 --value "OC\Preview\Photoshop"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 18 --value "OC\Preview\Postscript"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 19 --value "OC\Preview\StarOffice"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 20 --value "OC\Preview\SVG"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 21 --value "OC\Preview\TIFF"
    docker exec --user www-data roquio_nextcloud-app_1 php occ config:system:set enabledPreviewProviders 22 --value "OC\Preview\Font"

### Cron

    crontab -e

append this line:

    */5  *  *  *  * docker exec --user www-data roquio_nextcloud-app_1 php cron.php
    
### Certificat

    docker-compose run --rm certbot certonly --webroot --webroot-path /var/www/certbot/ --register-unsafely-without-email --dry-run -d cloud.roqu.io
    docker-compose run --rm certbot certonly --webroot --webroot-path /var/www/certbot/ -d cloud.roqu.io

### Certificat renew

    docker-compose run --rm certbot renew
