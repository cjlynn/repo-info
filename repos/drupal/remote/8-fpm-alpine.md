## `drupal:8-fpm-alpine`

```console
$ docker pull drupal@sha256:cd67bc634cbb58a76d1e38174402364a522914dc808cb28f095ec2359b1e23fc
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `drupal:8-fpm-alpine` - linux; amd64

```console
$ docker pull drupal@sha256:fa96993256d6a4a4e97bb30a561da34efe7f603e96484f1fc7685d2c27decef7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **47.5 MB (47494344 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:01fda8c3d7a0f66abf3cf218e06aa56c3294759be8e2604ab0d3c642322ded96`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Tue, 09 Jan 2018 21:12:40 GMT
ADD file:69848cb51056edaf120230b6f218a79968ac797295c2cef6728332e1801357be in / 
# Tue, 09 Jan 2018 21:12:40 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:00:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Wed, 10 Jan 2018 03:00:28 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		openssl
# Wed, 10 Jan 2018 03:00:35 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Wed, 10 Jan 2018 03:00:35 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Wed, 10 Jan 2018 03:00:36 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Wed, 10 Jan 2018 03:05:56 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Wed, 10 Jan 2018 03:05:57 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 10 Jan 2018 03:05:57 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 10 Jan 2018 03:05:57 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Wed, 10 Jan 2018 03:05:57 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Wed, 10 Jan 2018 03:05:58 GMT
ENV PHP_VERSION=7.1.13
# Wed, 10 Jan 2018 03:05:58 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Wed, 10 Jan 2018 03:05:58 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Wed, 10 Jan 2018 03:06:10 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Wed, 10 Jan 2018 03:06:10 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Wed, 10 Jan 2018 03:10:27 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		openssl-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Wed, 10 Jan 2018 03:16:05 GMT
COPY multi:f9544e5c6b9d1d1292fca43464fe1e77b631547ac2baa8503de318853c0536d0 in /usr/local/bin/ 
# Wed, 10 Jan 2018 03:16:05 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Wed, 10 Jan 2018 03:16:06 GMT
WORKDIR /var/www/html
# Wed, 10 Jan 2018 03:16:06 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Wed, 10 Jan 2018 03:16:07 GMT
EXPOSE 9000/tcp
# Wed, 10 Jan 2018 03:16:07 GMT
CMD ["php-fpm"]
# Wed, 10 Jan 2018 06:34:37 GMT
RUN set -ex 	&& apk add --no-cache --virtual .build-deps 		coreutils 		freetype-dev 		libjpeg-turbo-dev 		libpng-dev 		postgresql-dev 	&& docker-php-ext-configure gd 		--with-freetype-dir=/usr/include/ 		--with-jpeg-dir=/usr/include/ 		--with-png-dir=/usr/include/ 	&& docker-php-ext-install -j "$(nproc)" gd mbstring opcache pdo pdo_mysql pdo_pgsql zip 	&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .drupal-phpexts-rundeps $runDeps 	&& apk del .build-deps
# Wed, 10 Jan 2018 06:35:11 GMT
RUN { 		echo 'opcache.memory_consumption=128'; 		echo 'opcache.interned_strings_buffer=8'; 		echo 'opcache.max_accelerated_files=4000'; 		echo 'opcache.revalidate_freq=60'; 		echo 'opcache.fast_shutdown=1'; 		echo 'opcache.enable_cli=1'; 	} > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Wed, 10 Jan 2018 06:35:11 GMT
WORKDIR /var/www/html
# Wed, 10 Jan 2018 06:35:12 GMT
ENV DRUPAL_VERSION=8.4.4
# Wed, 10 Jan 2018 06:35:12 GMT
ENV DRUPAL_MD5=cfce3fb9293d8fe146f4c000505cb9b6
# Wed, 10 Jan 2018 06:35:16 GMT
RUN curl -fSL "https://ftp.drupal.org/files/projects/drupal-${DRUPAL_VERSION}.tar.gz" -o drupal.tar.gz 	&& echo "${DRUPAL_MD5} *drupal.tar.gz" | md5sum -c - 	&& tar -xz --strip-components=1 -f drupal.tar.gz 	&& rm drupal.tar.gz 	&& chown -R www-data:www-data sites modules themes
```

-	Layers:
	-	`sha256:81033e7c1d6a5b44a94bb6b40033a6e589f50fd6b61578da6fc809e61f83898d`  
		Last Modified: Tue, 09 Jan 2018 21:15:04 GMT  
		Size: 2.4 MB (2387570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:347280e4401ec27a2af6bcded9c9fe28c0acbe751f69f1d47c4fd6d2c82ba034`  
		Last Modified: Wed, 10 Jan 2018 04:40:03 GMT  
		Size: 1.3 MB (1324983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:575b1e17046fe1c06043ae027f4599ed64f34196604a884d74c8942cdf71873e`  
		Last Modified: Wed, 10 Jan 2018 04:40:02 GMT  
		Size: 1.3 KB (1274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b26c263d6f029c4ccdfe4f8da176f53cbf3870d7d83f852d8b05ec3a606374d9`  
		Last Modified: Wed, 10 Jan 2018 04:40:00 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3573932b56e4a515b232faaec22023a145405f9e7b5e7458897470f2bc07ca4b`  
		Last Modified: Wed, 10 Jan 2018 04:42:30 GMT  
		Size: 12.2 MB (12213973 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11deaf2936873207aa45250c0ade80cf246444dcbfa61c8207ab2274419045c6`  
		Last Modified: Wed, 10 Jan 2018 04:42:30 GMT  
		Size: 493.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2f0e97bc855a8e7cce811a6c2d3f239bb8f89082527b17ce6234cd0b6384e0e`  
		Last Modified: Wed, 10 Jan 2018 04:42:32 GMT  
		Size: 14.8 MB (14818163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3cd46707e491107335820cfc162f1f9557d2b6589c99709d67fb9a82c85bc07`  
		Last Modified: Wed, 10 Jan 2018 04:42:26 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2814e3b3bb4fdf4ce4e908ff68ccf1f9872582a4d47f836556120e4ea1756c19`  
		Last Modified: Wed, 10 Jan 2018 04:42:27 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5e4fe11845a6fae1742560914add4a3f686ef793daf4ce3647efe606ed2da8f`  
		Last Modified: Wed, 10 Jan 2018 04:42:26 GMT  
		Size: 7.7 KB (7670 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd9a3d5df7890266dbe2d895d5b2732013083e71a5715c6308884fec8d713a7e`  
		Last Modified: Wed, 10 Jan 2018 06:45:23 GMT  
		Size: 3.2 MB (3166374 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da5cd3ae1810b3b6ea77dd9fecbd6faee994c3376324269b04d5de3c1dbc61bf`  
		Last Modified: Wed, 10 Jan 2018 06:45:23 GMT  
		Size: 340.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4875c2931221bcf1fa2f80909bfd5f29039c98743fcddc01de5aaeb4dba0997`  
		Last Modified: Wed, 10 Jan 2018 06:45:40 GMT  
		Size: 13.6 MB (13571038 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
