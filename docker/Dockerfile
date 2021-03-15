FROM nextcloud:21.0.0-apache

RUN apt update \
 && apt upgrade \
 && mkdir -p /usr/share/man/man1 \
 && apt install -y libreoffice libreoffice-l10n-ru libreoffice-help-ru \
 && apt install -y ffmpeg imagemagick ghostscript \
 && rm -rf /var/lib/apt/lists/*

RUN cat /etc/ImageMagick-6/policy.xml | sed 's/domain="coder" rights="none"/domain="coder" rights="read|write"/' \
 | sed 's/domain="coder" rights="read|write" pattern="HTTP"/domain="coder" rights="none" pattern="HTTP"/' \
 | sed 's/domain="coder" rights="read|write" pattern="\*"/domain="coder" rights="none" pattern="\*"/' > /etc/ImageMagick-6/policy1.xml \
 && mv /etc/ImageMagick-6/policy.xml /etc/ImageMagick-6/policy2.xml \
 && mv /etc/ImageMagick-6/policy1.xml /etc/ImageMagick-6/policy.xml