## `bonita:latest`

```console
$ docker pull bonita@sha256:ebd44dcfad1a4527b15085aad5535eaff2a59fc998417f3c0e9bc7f97b55c6a0
```

-	Platforms:
	-	linux; amd64

### `bonita:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **217.8 MB (217848969 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ec9fa0503c819b35f214310097acfe9595a1c1c42c388f89c59e3b70e68ce92f`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Fri, 02 Jun 2017 16:16:32 GMT
ADD file:5aff8c59a70783352d1d5d5b24ddd27b77d9cdc5917992febe9d92901f78a8b3 in / 
# Fri, 02 Jun 2017 16:16:33 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 02 Jun 2017 16:16:35 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 02 Jun 2017 16:16:36 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 02 Jun 2017 16:16:38 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 02 Jun 2017 16:16:38 GMT
CMD ["/bin/bash"]
# Fri, 02 Jun 2017 17:34:00 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Fri, 02 Jun 2017 17:34:31 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   wget   zip   && rm -rf /var/lib/apt/lists/*
# Fri, 02 Jun 2017 17:34:33 GMT
RUN mkdir /opt/custom-init.d/
# Fri, 02 Jun 2017 17:34:34 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Fri, 02 Jun 2017 17:34:37 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Fri, 02 Jun 2017 17:35:00 GMT
RUN wget -q "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture)" -O /usr/local/bin/gosu   && wget -q "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture).asc" -O /usr/local/bin/gosu.asc   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Fri, 02 Jun 2017 17:35:01 GMT
ARG BONITA_VERSION
# Fri, 02 Jun 2017 17:35:02 GMT
ARG TOMCAT_VERSION
# Fri, 02 Jun 2017 17:35:03 GMT
ARG BONITA_SHA256
# Fri, 02 Jun 2017 17:35:04 GMT
ARG BONITA_URL
# Fri, 02 Jun 2017 17:35:05 GMT
ENV BONITA_VERSION=7.5.0
# Fri, 02 Jun 2017 17:35:05 GMT
ENV TOMCAT_VERSION=7.0.76
# Fri, 02 Jun 2017 17:35:06 GMT
ENV BONITA_SHA256=7784fa4febfbbe74d69ebc40a1e4848c00777bb3d8fdba5966be3bcbd5ccc0d9
# Fri, 02 Jun 2017 17:35:07 GMT
ENV BONITA_URL=http://download.forge.ow2.org/bonita/BonitaBPMCommunity-7.5.0-Tomcat-7.0.76.zip
# Fri, 02 Jun 2017 17:35:18 GMT
RUN mkdir /opt/files   && wget -q ${BONITA_URL} -O /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Fri, 02 Jun 2017 17:35:20 GMT
RUN sha256sum /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Fri, 02 Jun 2017 17:35:43 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Fri, 02 Jun 2017 17:35:43 GMT
VOLUME [/opt/bonita]
# Fri, 02 Jun 2017 17:35:45 GMT
COPY dir:14da98bbdef0a4f881fec1c4e63270b89b849fd97a1e073f69fe60f8f0498bb1 in /opt/files 
# Fri, 02 Jun 2017 17:35:46 GMT
COPY dir:0f5b28efb7aa0114806152fbcfef64599a58d3bd42d494d262f29d8f3408ea15 in /opt/templates 
# Fri, 02 Jun 2017 17:35:47 GMT
EXPOSE 8080/tcp
# Fri, 02 Jun 2017 17:35:47 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:bd97b43c27e332fc4e00edf827bbc26369ad375187ce6eee91c616ad275884b1`  
		Last Modified: Fri, 19 May 2017 22:35:30 GMT  
		Size: 46.9 MB (46933232 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6960dc1aba1816652969986284410927a5d942bf8042e077a3ebc8d1c58bb432`  
		Last Modified: Fri, 02 Jun 2017 16:23:28 GMT  
		Size: 814.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b61829b0db5f4033ff48cbf3495271c8410c76e6396b56f15a79c3f7b5b7845`  
		Last Modified: Fri, 02 Jun 2017 16:23:27 GMT  
		Size: 512.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f88dc826b144c661a8d1d08561e1ff3711f527042955505e9f3e563bdb2281f`  
		Last Modified: Fri, 02 Jun 2017 16:23:28 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73b3859b1e43f3ff32f10055951a568a9ad5ab6dc4ab61818b117b6912088f3d`  
		Last Modified: Fri, 02 Jun 2017 16:23:28 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7377b0deb3bbfad2c535d96d9ae1d9debe35ae23d40e02167824b48cebfe8783`  
		Last Modified: Fri, 02 Jun 2017 17:37:25 GMT  
		Size: 82.6 MB (82572086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b43332da42eef618e6f2d9227178d26f165af221c7c4bbb7ff762d7d391a4623`  
		Last Modified: Fri, 02 Jun 2017 17:37:09 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:286c7d64a987f5c1f376bd1538d53529746bfef0540b1cd9ebd1e345d4cc08e5`  
		Last Modified: Fri, 02 Jun 2017 17:37:07 GMT  
		Size: 2.0 KB (2004 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06e6ac5ebdabb5ad46cc77c6c86e674a2f61604dbec070c6094eb48be900d2f8`  
		Last Modified: Fri, 02 Jun 2017 17:37:07 GMT  
		Size: 123.2 KB (123240 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2abbd83405539d414dd078b68dcd1442d853efa055f765d8cb5710fa1391d03e`  
		Last Modified: Fri, 02 Jun 2017 17:37:08 GMT  
		Size: 818.7 KB (818735 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28b5dec9e74abbeb6a6544891ece39641dfc372f39f8a8b09e7d33be04a93ef4`  
		Last Modified: Fri, 02 Jun 2017 17:37:14 GMT  
		Size: 87.4 MB (87389582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc7244dfbc52c294f129e698a2b7cd668926b6d70806bfb020c684ade682fd4b`  
		Last Modified: Fri, 02 Jun 2017 17:37:07 GMT  
		Size: 6.0 KB (6021 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:386d264bd070095db639874eceda29536c7a25f11f61f018a529761b302a77c0`  
		Last Modified: Fri, 02 Jun 2017 17:37:07 GMT  
		Size: 1.6 KB (1608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
