FROM bitnami/minideb-extras:stretch-r199
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages ghostscript imagemagick libbsd0 libbz2-1.0 libc6 libcomerr2 libcurl3 libedit2 libexpat1 libffi6 libfftw3-double3 libfontconfig1 libfreetype6 libgcc1 libgcrypt20 libglib2.0-0 libgmp-dev libgmp10 libgnutls30 libgomp1 libgpg-error0 libgssapi-krb5-2 libhogweed4 libicu57 libidn11 libidn2-0 libk5crypto3 libkeyutils1 libkrb5-3 libkrb5support0 liblcms2-2 libldap-2.4-2 liblqr-1-0 libltdl7 liblzma5 libmagickcore-6.q16-3 libmagickwand-6.q16-3 libmariadbclient18 libncurses5 libnettle6 libnghttp2-14 libp11-kit0 libpcre3 libpng16-16 libpq5 libpsl5 libreadline7 librtmp1 libsasl2-2 libssh2-1 libssl1.0.2 libssl1.1 libstdc++6 libtasn1-6 libtinfo5 libunistring0 libx11-6 libxau6 libxcb1 libxdmcp6 libxext6 libxml2 libxml2-dev libxslt1-dev libxslt1.1 zlib1g zlib1g-dev
RUN bitnami-pkg install ruby-2.4.5-0 --checksum 6b8fe1a5db54cc642125e96caf239329d27b2871cd0830a4158c312668a2afc7
RUN bitnami-pkg install postgresql-client-9.6.11-0 --checksum f1825273d8f7a0c88fecf6e3f91e9bc940ce1f8b69add7dfa14aca51d15209aa
RUN bitnami-pkg install mysql-client-10.1.37-0 --checksum 2d73953a0a8f630163e14308737b97541a8cbcdafdb1efeb5a2138e720d3de14
RUN bitnami-pkg install git-2.19.1-2 --checksum afed897918bbbf73d72e4cb9b72e30dc43b09ed322d390e0cee889ee75c2e080
RUN bitnami-pkg unpack redmine-3.4.6-4 --checksum e6c9e9331b668b30009eb128cfaacc900daf7ef51447dffe241c5b6c051276f4

COPY rootfs /
ENV BITNAMI_APP_NAME="redmine" \
    BITNAMI_IMAGE_VERSION="3.4.6-debian-9-r89" \
    PATH="/opt/bitnami/ruby/bin:/opt/bitnami/postgresql/bin:/opt/bitnami/mysql/bin:/opt/bitnami/git/bin:$PATH" \
    REDMINE_DB_MYSQL="mariadb" \
    REDMINE_DB_PASSWORD="" \
    REDMINE_DB_PORT_NUMBER="" \
    REDMINE_DB_POSTGRES="" \
    REDMINE_DB_USERNAME="" \
    REDMINE_EMAIL="user@example.com" \
    REDMINE_LANGUAGE="en" \
    REDMINE_PASSWORD="bitnami1" \
    REDMINE_USERNAME="user" \
    SMTP_HOST="" \
    SMTP_PASSWORD="" \
    SMTP_PORT="" \
    SMTP_TLS="true" \
    SMTP_USER=""

EXPOSE 3000

ENTRYPOINT [ "/app-entrypoint.sh" ]
CMD [ "/run.sh" ]
