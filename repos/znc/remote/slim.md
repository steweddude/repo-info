## `znc:slim`

```console
$ docker pull znc@sha256:8f40c31cf24b2f5e06b747e7ce40d97f57bd29dffc19fa9a3f9fcc268cd4efe8
```

-	Platforms:
	-	linux; amd64

### `znc:slim` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **23.9 MB (23854753 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:28d406b77bce6a9cbf2de6fa7ea540b7f080a41ae865b2a79101add4b3c159c1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Tue, 28 Feb 2017 23:59:25 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Tue, 28 Feb 2017 23:59:25 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Tue, 28 Feb 2017 23:59:25 GMT
ARG MAKEFLAGS=
# Tue, 28 Feb 2017 23:59:26 GMT
ENV ZNC_VERSION=1.6.4
# Wed, 01 Mar 2017 00:50:36 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         openssl         tini     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         openssl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "http://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "http://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 01 Mar 2017 00:50:48 GMT
COPY file:e05a8b743f8314062b8181a6e6635452aaf4c0cb244920409faa0b1555827b58 in / 
# Wed, 01 Mar 2017 00:50:48 GMT
USER [znc]
# Wed, 01 Mar 2017 00:50:49 GMT
VOLUME [/znc-data]
# Wed, 01 Mar 2017 00:50:49 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de1f70d6790d488e5a2159805ece2248b3bbcfe60a7f1e3f16c882f33be6fc3a`  
		Last Modified: Wed, 01 Mar 2017 00:52:31 GMT  
		Size: 22.0 MB (21952129 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58597475b629d93fd37a516eaa75e58c41f940c3975ae2168fe817a2dd56583d`  
		Last Modified: Wed, 01 Mar 2017 00:52:23 GMT  
		Size: 561.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip