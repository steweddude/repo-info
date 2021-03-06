## `php-zendserver:latest`

```console
$ docker pull php-zendserver@sha256:17f7c41a18c73e4fdfd42c51b9981bb46e9e8ef92a1536120ba022001a3b2652
```

-	Platforms:
	-	linux; amd64

### `php-zendserver:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **413.8 MB (413750837 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a87b780f3be21753f26cd7dffefa333321d162880e39b974f8f8bed4f1224e3f`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Fri, 02 Jun 2017 16:15:37 GMT
ADD file:1ad6d6b4b456510256c9561c6472b088a99a1858d86058e11408fc96112a3cee in / 
# Fri, 02 Jun 2017 16:15:39 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 02 Jun 2017 16:15:41 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 02 Jun 2017 16:15:42 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 02 Jun 2017 16:15:44 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 02 Jun 2017 16:15:44 GMT
CMD ["/bin/bash"]
# Sat, 03 Jun 2017 00:18:42 GMT
RUN apt-key adv --keyserver pgp.mit.edu --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623
# Sat, 03 Jun 2017 00:34:29 GMT
RUN echo "deb http://repos.zend.com/zend-server/9.1/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list
# Sat, 03 Jun 2017 00:37:06 GMT
RUN apt-get update && apt-get install -y libmysqlclient18 unzip git zend-server-php-7.1=9.1.0+b93 && /usr/local/zend/bin/zendctl.sh stop
# Sat, 03 Jun 2017 00:37:19 GMT
COPY file:9302000aa37d879e280a25b18913689dc42f94e2ab4a489f62a9eef3a0d1b76b in /etc/ 
# Sat, 03 Jun 2017 00:37:20 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Sat, 03 Jun 2017 00:37:43 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header
# Sat, 03 Jun 2017 00:37:44 GMT
RUN /usr/sbin/a2enmod headers
# Sat, 03 Jun 2017 00:38:05 GMT
ENV ZS_INIT_VERSION=0.2
# Sat, 03 Jun 2017 00:38:06 GMT
ENV ZS_INIT_SHA256=1c5cf557daf48cf018dba1cf46208f215d3b5fab47c73ff2d39988581ebd6932
# Sat, 03 Jun 2017 00:38:13 GMT
RUN apt-get install -y curl
# Sat, 03 Jun 2017 00:38:15 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Sat, 03 Jun 2017 00:38:37 GMT
WORKDIR /usr/local/zs-init
# Sat, 03 Jun 2017 00:38:43 GMT
RUN /usr/local/zend/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/zend/bin/php
# Sat, 03 Jun 2017 00:39:26 GMT
RUN /usr/local/zend/bin/php composer.phar update
# Sat, 03 Jun 2017 00:39:28 GMT
COPY dir:6174d7fdcd8142a1b143e80efd2994e57dd5d7610a8fbfee3a7288ddf495dfdf in /usr/local/bin 
# Sat, 03 Jun 2017 00:39:29 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Sat, 03 Jun 2017 00:39:30 GMT
RUN rm /var/www/html/index.html
# Sat, 03 Jun 2017 00:39:32 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Sat, 03 Jun 2017 00:39:32 GMT
EXPOSE 80/tcp
# Sat, 03 Jun 2017 00:39:33 GMT
EXPOSE 443/tcp
# Sat, 03 Jun 2017 00:39:34 GMT
EXPOSE 10081/tcp
# Sat, 03 Jun 2017 00:39:35 GMT
EXPOSE 10082/tcp
# Sat, 03 Jun 2017 00:39:36 GMT
WORKDIR /var/www/html
# Sat, 03 Jun 2017 00:39:36 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:1d8592394ba1ae81037e16fac3382070ce1478cf7f6c68d538c62ba067e111db`  
		Last Modified: Fri, 02 Jun 2017 16:21:26 GMT  
		Size: 67.1 MB (67110196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01aa7f61ccd17f0a729b91e6ba4ae6aedb51ca43acb3244b9732dbc043814786`  
		Last Modified: Fri, 02 Jun 2017 16:20:56 GMT  
		Size: 72.6 KB (72620 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5dd2552a960ee746b6272c9a7d2b3a252e07bf8ef38a0c8df117e0d96bf44904`  
		Last Modified: Fri, 02 Jun 2017 16:20:56 GMT  
		Size: 356.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7cbe941c5e3e55212fc2b56ef27a44b887b24bf163a3c1fbda2023265355d088`  
		Last Modified: Fri, 02 Jun 2017 16:20:56 GMT  
		Size: 676.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2549ecfb14c6934eb6ff9c45f15839db6abf3bdfbc617589f53ae4f67f265629`  
		Last Modified: Fri, 02 Jun 2017 16:20:56 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:301b914347183bc6c00db2421b478e9f9b03021f43fa463a0bc5cd0a529eeff1`  
		Last Modified: Sat, 03 Jun 2017 00:40:30 GMT  
		Size: 13.1 KB (13057 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0eb18a449ad92168f04a5690e77de0fdfb2a880271ec4cd9d7995a9cf644ef9b`  
		Last Modified: Sat, 03 Jun 2017 00:46:06 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe282e5f32975b3ee58e6ebfed0388cdf3f4103f08b53ba50935caea82db2a0d`  
		Last Modified: Sat, 03 Jun 2017 00:47:08 GMT  
		Size: 334.5 MB (334509315 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bde36d86bbba1e6173fb22a70cf92761d16930862e9d48f80de8ba066284a8a7`  
		Last Modified: Sat, 03 Jun 2017 00:46:06 GMT  
		Size: 217.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f21a91b9d693c9d64692b5b60a023c7c2c172262aa8e60f159a591b16de92d69`  
		Last Modified: Sat, 03 Jun 2017 00:46:04 GMT  
		Size: 255.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1acfd7768cb1743523c2641501eb6c2605dc483fe540b5082ea9c10f353477c3`  
		Last Modified: Sat, 03 Jun 2017 00:46:04 GMT  
		Size: 301.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcd82f070ac080fd4b71d19f0ea5c237afa75c976008a45c0dad31549a73976`  
		Last Modified: Sat, 03 Jun 2017 00:46:04 GMT  
		Size: 290.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c655ab225636d05c6b9cb46e580284e46c229ac386cf2705d1e3bed525b3385`  
		Last Modified: Sat, 03 Jun 2017 00:46:04 GMT  
		Size: 470.2 KB (470184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:703ec2ba8e0a901efb0c6593ad09afe04dd102e1b9f2833762fe43a6d6705877`  
		Last Modified: Sat, 03 Jun 2017 00:46:04 GMT  
		Size: 15.7 KB (15679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:469e3b6189ed2025d4ea37f7fac8640f8901bf8ba083ef6c096584ab0b7d8761`  
		Last Modified: Sat, 03 Jun 2017 00:46:01 GMT  
		Size: 489.4 KB (489420 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d4b2bd9f86fd89cf626d04c39928eca6bc35c2a824c255b897a6562940969cb`  
		Last Modified: Sat, 03 Jun 2017 00:46:04 GMT  
		Size: 11.1 MB (11050616 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1e422b7f75f7fd967c02d7e24b893c1fe189004ae7418aed8448026990e202d`  
		Last Modified: Sat, 03 Jun 2017 00:46:01 GMT  
		Size: 13.3 KB (13341 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce120623326a32d2ced0e2275494b43403a3722b2684411df2aa9d47d242047b`  
		Last Modified: Sat, 03 Jun 2017 00:46:01 GMT  
		Size: 2.5 KB (2513 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e705ec11ed2798e377ce3f9493a60658f95302401ce1e06dab90140be999c15`  
		Last Modified: Sat, 03 Jun 2017 00:46:01 GMT  
		Size: 166.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a829631a979bdb93f5a5fe3248052caa77424b3ce80a916aaac6b0f67ebd605c`  
		Last Modified: Sat, 03 Jun 2017 00:46:01 GMT  
		Size: 1.2 KB (1242 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
