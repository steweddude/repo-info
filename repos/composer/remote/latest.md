## `composer:latest`

```console
$ docker pull composer@sha256:3375a4e9f9e6a1e2c49449c75d463b1f3d3f74677780c5c484f1d5a423d222d4
```

-	Platforms:
	-	linux; amd64

### `composer:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55938486 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1556070756238ec380a2e26775f0aa51672969a1e79e6e6e2a94731456e42d3e`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Thu, 25 May 2017 23:31:54 GMT
ADD file:c34582524a7c4fa2ccb67d48efaa6edacff8bc8115a26a511b2385a03f56aa8e in / 
# Thu, 25 May 2017 23:31:55 GMT
CMD ["/bin/sh"]
# Fri, 26 May 2017 14:39:18 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Fri, 26 May 2017 14:39:22 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Fri, 26 May 2017 14:39:24 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 26 May 2017 14:39:25 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 26 May 2017 14:39:26 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 26 May 2017 14:39:27 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 26 May 2017 14:39:27 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 26 May 2017 14:39:28 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 26 May 2017 14:39:29 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Fri, 26 May 2017 14:39:30 GMT
ENV PHP_VERSION=7.1.5
# Fri, 26 May 2017 14:39:30 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Fri, 26 May 2017 14:39:31 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Fri, 26 May 2017 14:39:39 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 26 May 2017 14:39:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Fri, 02 Jun 2017 19:00:29 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Fri, 02 Jun 2017 19:03:27 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Fri, 02 Jun 2017 19:03:28 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Fri, 02 Jun 2017 19:03:28 GMT
CMD ["php" "-a"]
# Mon, 05 Jun 2017 15:36:29 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Mon, 05 Jun 2017 15:36:44 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Mon, 05 Jun 2017 15:36:45 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 05 Jun 2017 15:36:45 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Mon, 05 Jun 2017 15:36:46 GMT
ENV COMPOSER_HOME=/composer
# Mon, 05 Jun 2017 15:38:00 GMT
ENV COMPOSER_VERSION=1.4.2
# Mon, 05 Jun 2017 15:38:04 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Mon, 05 Jun 2017 15:38:25 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Mon, 05 Jun 2017 15:38:26 GMT
WORKDIR /app
# Mon, 05 Jun 2017 15:38:27 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 05 Jun 2017 15:38:28 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:486a8e636d6250a74d15cdb3582f4dd198271a80118f5a2f59de3d9cd8433611`  
		Last Modified: Thu, 25 May 2017 23:35:56 GMT  
		Size: 2.4 MB (2383064 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41812ec2cb654115fad6678a89cace781f0cf539e2316efe2005438e428db6df`  
		Last Modified: Fri, 26 May 2017 15:25:24 GMT  
		Size: 1.1 MB (1081315 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e095add676785194f9c4d180e50bdeb9eac882406547f0428cf26be373adff6b`  
		Last Modified: Fri, 26 May 2017 15:25:21 GMT  
		Size: 1.3 KB (1275 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:286dbb174b8d2bb248dcfc542bb4edd08165b8fd2d01f9fbf7ff36c68c8ee43c`  
		Last Modified: Fri, 26 May 2017 15:25:21 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2dd98f4659aaf3137febe1466589df190f9c1e7db80a9fa7ef2a63db2ac79724`  
		Last Modified: Fri, 26 May 2017 15:25:22 GMT  
		Size: 13.0 MB (12971396 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:215189fa3485f90be9faab67dc10aacbd365c2bb2f40fe444e02a4484e6e9b7b`  
		Last Modified: Fri, 26 May 2017 15:25:21 GMT  
		Size: 485.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3645f6816af1a5e8985f2ab0b3e1918d8e7e8de83393f78746d80eca18c2f668`  
		Last Modified: Sat, 03 Jun 2017 00:06:55 GMT  
		Size: 10.7 MB (10748155 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8a4b81050fba74ee4fe1aa800350e6688f3db450b079a92b7fd44d0b68116f5`  
		Last Modified: Sat, 03 Jun 2017 00:06:51 GMT  
		Size: 2.1 KB (2107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b539bc53a30c23c34bc1f7a50b420c5bdeb6ddf4acc4f0c8469e0f7388fe0e2d`  
		Last Modified: Mon, 05 Jun 2017 15:38:59 GMT  
		Size: 28.3 MB (28260163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a18648842a29c0d455fdf9188c7bbe053cfad9cd743d4939d1ebe943fa7237d4`  
		Last Modified: Mon, 05 Jun 2017 15:38:54 GMT  
		Size: 267.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5361efcb503e232d8aad7c498909b55ad92897de3afe5a9ead5946069e48572e`  
		Last Modified: Mon, 05 Jun 2017 15:39:54 GMT  
		Size: 489.5 KB (489473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7b1852fae631014857d88ff3abfeb8ef5af3dd5ce4ed8f31d96ab44f70e332a`  
		Last Modified: Mon, 05 Jun 2017 15:39:52 GMT  
		Size: 529.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2389812dcfb83e31b8c715d5b72ee471f6816785b28268f758d145d9b4f37686`  
		Last Modified: Mon, 05 Jun 2017 15:39:52 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
