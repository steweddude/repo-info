## `redmine:passenger`

```console
$ docker pull redmine@sha256:82b93015664af9065a28bded49a91af3e547cd03b70430be308a42e69e82098f
```

-	Platforms:
	-	linux; amd64

### `redmine:passenger` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **271.7 MB (271667387 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a8204896cfb93a7c70d33d896d9685d287f4b54edef5d0df8ec1c89f70be5ab9`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 15:53:10 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:53:12 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Wed, 10 May 2017 16:00:06 GMT
ENV RUBY_MAJOR=2.2
# Wed, 10 May 2017 16:00:06 GMT
ENV RUBY_VERSION=2.2.7
# Wed, 10 May 2017 16:00:07 GMT
ENV RUBY_DOWNLOAD_SHA256=234c8aee6543da9efd67008e6e7ee740d41ed57a52e797f65043c3b5ec3bcb53
# Wed, 10 May 2017 16:00:08 GMT
ENV RUBYGEMS_VERSION=2.6.12
# Thu, 11 May 2017 18:47:33 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Sat, 03 Jun 2017 19:18:55 GMT
ENV BUNDLER_VERSION=1.15.1
# Sat, 03 Jun 2017 19:18:58 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Sat, 03 Jun 2017 19:18:59 GMT
ENV GEM_HOME=/usr/local/bundle
# Sat, 03 Jun 2017 19:19:00 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Sat, 03 Jun 2017 19:19:01 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 03 Jun 2017 19:19:02 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Sat, 03 Jun 2017 19:19:03 GMT
CMD ["irb"]
# Mon, 05 Jun 2017 14:58:11 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Mon, 05 Jun 2017 14:58:26 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 05 Jun 2017 14:58:26 GMT
ENV GOSU_VERSION=1.7
# Mon, 05 Jun 2017 14:58:33 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Mon, 05 Jun 2017 14:58:34 GMT
ENV TINI_VERSION=v0.9.0
# Mon, 05 Jun 2017 14:58:37 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Mon, 05 Jun 2017 14:59:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		imagemagick 		libmysqlclient18 		libpq5 		libsqlite3-0 				bzr 		git 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Mon, 05 Jun 2017 15:00:35 GMT
ENV RAILS_ENV=production
# Mon, 05 Jun 2017 15:00:37 GMT
WORKDIR /usr/src/redmine
# Mon, 05 Jun 2017 15:23:50 GMT
ENV REDMINE_VERSION=3.3.3
# Mon, 05 Jun 2017 15:23:51 GMT
ENV REDMINE_DOWNLOAD_MD5=c946839c9a51dba48ae7c34c5351f677
# Mon, 05 Jun 2017 15:23:55 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Mon, 05 Jun 2017 15:26:33 GMT
RUN buildDeps=' 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	' 	&& set -ex 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends 	&& rm -rf /var/lib/apt/lists/* 	&& bundle install --without development test 	&& for adapter in mysql2 postgresql sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 	done 	&& rm ./config/database.yml 	&& apt-get purge -y --auto-remove $buildDeps
# Mon, 05 Jun 2017 15:26:35 GMT
VOLUME [/usr/src/redmine/files]
# Mon, 05 Jun 2017 15:26:36 GMT
COPY file:5efb6ca648b54af01740423ca0fdde905eae0ce732d8f2683c79dcf93e0e86c5 in / 
# Mon, 05 Jun 2017 15:26:36 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 05 Jun 2017 15:26:38 GMT
EXPOSE 3000/tcp
# Mon, 05 Jun 2017 15:26:39 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Mon, 05 Jun 2017 15:27:03 GMT
ENV PASSENGER_VERSION=5.1.4
# Mon, 05 Jun 2017 15:27:20 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Mon, 05 Jun 2017 15:27:35 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Mon, 05 Jun 2017 15:27:36 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0aaa89427703d5bdd37a7b3c98c01a6e0434e2906c7212919ed6277622bf9abb`  
		Last Modified: Thu, 11 May 2017 19:23:22 GMT  
		Size: 10.2 MB (10159984 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e4351445696bc2482da72ce5d84caf70003361f2997c9b7e2adae06a3725118`  
		Last Modified: Thu, 11 May 2017 19:23:19 GMT  
		Size: 201.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72c399ee88adc9c41869a4d43d7adf200cd366d681b8a37e8496ce79f80a14b2`  
		Last Modified: Thu, 11 May 2017 19:27:58 GMT  
		Size: 33.8 MB (33805598 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd4fc9895ed7366fa431f49d83bfe41aeab3e790f204bd545bdc873652dfb093`  
		Last Modified: Sat, 03 Jun 2017 19:36:10 GMT  
		Size: 677.9 KB (677902 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00facae99acf680b48a1f6fe74a8e2037f4d924c7b23a04f7eb8c9b086a1681b`  
		Last Modified: Sat, 03 Jun 2017 19:36:10 GMT  
		Size: 159.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39fe42e23efc1144576c101bdd36cb76c7109f04213ee69e9e55dc54c0f31e03`  
		Last Modified: Mon, 05 Jun 2017 15:28:05 GMT  
		Size: 2.1 KB (2068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adcb648331635478d55b7743d8831bc23b397b86062af78eee0adb2b212c39b1`  
		Last Modified: Mon, 05 Jun 2017 15:28:09 GMT  
		Size: 14.4 MB (14426674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:605738c68599197ae2e1fca173c60e31b920d60d1285e9c139bc4f52fcaf9c3a`  
		Last Modified: Mon, 05 Jun 2017 15:28:06 GMT  
		Size: 818.8 KB (818812 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb8b57703d24feaf2ff6d936f5a288c8cacf2d1e63319c2a5238eedb8e144c09`  
		Last Modified: Mon, 05 Jun 2017 15:28:03 GMT  
		Size: 7.3 KB (7288 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0d2fec5a47390782b1479736fae1ff0b819e3b1027139020696dce0cd99b63d`  
		Last Modified: Mon, 05 Jun 2017 15:28:23 GMT  
		Size: 60.9 MB (60933366 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bd6e321e44954d6608b053ee2a01c20d68e613f8891df8a89c4b1a0124273cc`  
		Last Modified: Mon, 05 Jun 2017 15:28:03 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:509199c744bc6f604f68d2d25a187b7fd458218cbb5a692017ec2424c09200ed`  
		Last Modified: Mon, 05 Jun 2017 15:34:15 GMT  
		Size: 2.4 MB (2388312 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72bc2865edcf89ceacd760632418ac94f21b4230fa1685d59807ab56a951290a`  
		Last Modified: Mon, 05 Jun 2017 15:34:23 GMT  
		Size: 76.6 MB (76598244 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89bcf430a5580a21e16c4f7b737f932859860dedff60ca37b844b6a264a6a72f`  
		Last Modified: Mon, 05 Jun 2017 15:34:13 GMT  
		Size: 1.5 KB (1537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a510b05928a016b13ee7eae35072c4fa5f6114b7a9f88760b3f20a8674b45c3`  
		Last Modified: Mon, 05 Jun 2017 15:36:48 GMT  
		Size: 15.1 MB (15063202 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9da6c3c51c8688e67414f43b3b152ac6c87f60472f6a7bc0fe8f976c4c8ea58a`  
		Last Modified: Mon, 05 Jun 2017 15:36:47 GMT  
		Size: 4.2 MB (4199893 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
