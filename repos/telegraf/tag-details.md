<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `telegraf`

-	[`telegraf:1.2`](#telegraf12)
-	[`telegraf:1.2.1`](#telegraf121)
-	[`telegraf:1.2-alpine`](#telegraf12-alpine)
-	[`telegraf:1.2.1-alpine`](#telegraf121-alpine)
-	[`telegraf:1.3`](#telegraf13)
-	[`telegraf:1.3.1`](#telegraf131)
-	[`telegraf:latest`](#telegraflatest)
-	[`telegraf:1.3-alpine`](#telegraf13-alpine)
-	[`telegraf:1.3.1-alpine`](#telegraf131-alpine)
-	[`telegraf:alpine`](#telegrafalpine)

## `telegraf:1.2`

```console
$ docker pull telegraf@sha256:516c40ba436c364ada7c0be9aebef23bbf426b87771c2a79672b576ff81f57a9
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.2` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **81.8 MB (81839882 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:be5c0ae03290c6b6a2b191302d9a154694cf2605bc6eca4ac34578204f9186fb`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

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
# Fri, 02 Jun 2017 17:07:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 04:59:30 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Sat, 03 Jun 2017 04:59:31 GMT
ENV TELEGRAF_VERSION=1.2.1
# Sat, 03 Jun 2017 04:59:37 GMT
RUN wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}_amd64.deb.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}_amd64.deb &&     gpg --batch --verify telegraf_${TELEGRAF_VERSION}_amd64.deb.asc telegraf_${TELEGRAF_VERSION}_amd64.deb &&     dpkg -i telegraf_${TELEGRAF_VERSION}_amd64.deb &&     rm -f telegraf_${TELEGRAF_VERSION}_amd64.deb*
# Sat, 03 Jun 2017 04:59:38 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Sat, 03 Jun 2017 04:59:40 GMT
COPY file:7211de01f296351833389a1a1879d450e2cb727d7e2910d5807937f99983edf7 in /entrypoint.sh 
# Sat, 03 Jun 2017 04:59:40 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 03 Jun 2017 04:59:41 GMT
CMD ["telegraf"]
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
	-	`sha256:3c5e13aa4be9211a1b0511b6920b59ea9f46d7c0689e7d23d966e2fa3959ef24`  
		Last Modified: Fri, 02 Jun 2017 17:30:38 GMT  
		Size: 4.7 MB (4705680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec76e021997cff53c7c748e501851968bb34d36c7755514396a414ce0277d800`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 6.9 KB (6881 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9cbddefb697d11858d4388957e33b0ba15a58f07d7ed239c12041db91d3b921`  
		Last Modified: Sat, 03 Jun 2017 05:00:42 GMT  
		Size: 9.9 MB (9943125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d62f7bc08c57c956d97461f0f17940fbd864178ea0fa41f1320f892daaaa9f0`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 185.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.2.1`

```console
$ docker pull telegraf@sha256:516c40ba436c364ada7c0be9aebef23bbf426b87771c2a79672b576ff81f57a9
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.2.1` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **81.8 MB (81839882 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:be5c0ae03290c6b6a2b191302d9a154694cf2605bc6eca4ac34578204f9186fb`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

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
# Fri, 02 Jun 2017 17:07:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 04:59:30 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Sat, 03 Jun 2017 04:59:31 GMT
ENV TELEGRAF_VERSION=1.2.1
# Sat, 03 Jun 2017 04:59:37 GMT
RUN wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}_amd64.deb.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}_amd64.deb &&     gpg --batch --verify telegraf_${TELEGRAF_VERSION}_amd64.deb.asc telegraf_${TELEGRAF_VERSION}_amd64.deb &&     dpkg -i telegraf_${TELEGRAF_VERSION}_amd64.deb &&     rm -f telegraf_${TELEGRAF_VERSION}_amd64.deb*
# Sat, 03 Jun 2017 04:59:38 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Sat, 03 Jun 2017 04:59:40 GMT
COPY file:7211de01f296351833389a1a1879d450e2cb727d7e2910d5807937f99983edf7 in /entrypoint.sh 
# Sat, 03 Jun 2017 04:59:40 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 03 Jun 2017 04:59:41 GMT
CMD ["telegraf"]
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
	-	`sha256:3c5e13aa4be9211a1b0511b6920b59ea9f46d7c0689e7d23d966e2fa3959ef24`  
		Last Modified: Fri, 02 Jun 2017 17:30:38 GMT  
		Size: 4.7 MB (4705680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec76e021997cff53c7c748e501851968bb34d36c7755514396a414ce0277d800`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 6.9 KB (6881 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9cbddefb697d11858d4388957e33b0ba15a58f07d7ed239c12041db91d3b921`  
		Last Modified: Sat, 03 Jun 2017 05:00:42 GMT  
		Size: 9.9 MB (9943125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d62f7bc08c57c956d97461f0f17940fbd864178ea0fa41f1320f892daaaa9f0`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 185.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.2-alpine`

```console
$ docker pull telegraf@sha256:c67445b6f7fbdc3c2c210b7287430df401f4250d5d9f7e27a00796303ee59805
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.2-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **9.4 MB (9414854 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:893c16c608e73178dc7f63949ae838fa3d09480b21a432041a74301bd39b5b9e`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Thu, 25 May 2017 23:32:38 GMT
ADD file:df15515197b183747a0b7ccefd75973edc87fc7a5bce30fa10ae94e75928d25c in / 
# Thu, 25 May 2017 23:32:38 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 16:29:15 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Thu, 01 Jun 2017 23:56:17 GMT
RUN apk add --no-cache iputils ca-certificates &&     update-ca-certificates
# Thu, 01 Jun 2017 23:56:18 GMT
ENV TELEGRAF_VERSION=1.2.1
# Thu, 01 Jun 2017 23:56:28 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Thu, 01 Jun 2017 23:56:29 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Thu, 01 Jun 2017 23:56:30 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Thu, 01 Jun 2017 23:56:31 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 01 Jun 2017 23:56:31 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:6f821164d5b7ec94868795c1fb8dc6fd7d1fe51e04f97a6cf3a487868f2f5d68`  
		Last Modified: Thu, 25 May 2017 23:36:24 GMT  
		Size: 2.0 MB (1967927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fb7a10a08f9c25306f2f520f46b33d97a83c5a4138ad35810dad882d0982231`  
		Last Modified: Tue, 30 May 2017 16:30:02 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46f61cc0c7d37271f541554621a5e0adf8f74f958cf4a865c0473ed60a6b3138`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 447.4 KB (447402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6b0adfb0f498af1a287e85924ad16283c1479a85e5596683e2bcb9cf566413c`  
		Last Modified: Fri, 02 Jun 2017 00:00:21 GMT  
		Size: 7.0 MB (6999188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6ea2f42cacef536d3b998ccc679405d66f26d85765029d8a8e8c36f3d1e2400`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.2.1-alpine`

```console
$ docker pull telegraf@sha256:c67445b6f7fbdc3c2c210b7287430df401f4250d5d9f7e27a00796303ee59805
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.2.1-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **9.4 MB (9414854 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:893c16c608e73178dc7f63949ae838fa3d09480b21a432041a74301bd39b5b9e`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Thu, 25 May 2017 23:32:38 GMT
ADD file:df15515197b183747a0b7ccefd75973edc87fc7a5bce30fa10ae94e75928d25c in / 
# Thu, 25 May 2017 23:32:38 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 16:29:15 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Thu, 01 Jun 2017 23:56:17 GMT
RUN apk add --no-cache iputils ca-certificates &&     update-ca-certificates
# Thu, 01 Jun 2017 23:56:18 GMT
ENV TELEGRAF_VERSION=1.2.1
# Thu, 01 Jun 2017 23:56:28 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Thu, 01 Jun 2017 23:56:29 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Thu, 01 Jun 2017 23:56:30 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Thu, 01 Jun 2017 23:56:31 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 01 Jun 2017 23:56:31 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:6f821164d5b7ec94868795c1fb8dc6fd7d1fe51e04f97a6cf3a487868f2f5d68`  
		Last Modified: Thu, 25 May 2017 23:36:24 GMT  
		Size: 2.0 MB (1967927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fb7a10a08f9c25306f2f520f46b33d97a83c5a4138ad35810dad882d0982231`  
		Last Modified: Tue, 30 May 2017 16:30:02 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46f61cc0c7d37271f541554621a5e0adf8f74f958cf4a865c0473ed60a6b3138`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 447.4 KB (447402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6b0adfb0f498af1a287e85924ad16283c1479a85e5596683e2bcb9cf566413c`  
		Last Modified: Fri, 02 Jun 2017 00:00:21 GMT  
		Size: 7.0 MB (6999188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6ea2f42cacef536d3b998ccc679405d66f26d85765029d8a8e8c36f3d1e2400`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.3`

```console
$ docker pull telegraf@sha256:ada005b2e652e50a34338b006f8147095ac9d9f65429070f1e72862d006f3faf
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.3` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83444325 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bd66ca8c5f5864eac119c161721df7364040e41689b5fa5725600a6c155c24e5`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

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
# Fri, 02 Jun 2017 17:07:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 04:59:30 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Sat, 03 Jun 2017 05:00:06 GMT
ENV TELEGRAF_VERSION=1.3.1
# Sat, 03 Jun 2017 05:00:10 GMT
RUN wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}-1_amd64.deb.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     gpg --batch --verify telegraf_${TELEGRAF_VERSION}-1_amd64.deb.asc telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     dpkg -i telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     rm -f telegraf_${TELEGRAF_VERSION}-1_amd64.deb*
# Sat, 03 Jun 2017 05:00:11 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Sat, 03 Jun 2017 05:00:12 GMT
COPY file:7211de01f296351833389a1a1879d450e2cb727d7e2910d5807937f99983edf7 in /entrypoint.sh 
# Sat, 03 Jun 2017 05:00:13 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 03 Jun 2017 05:00:14 GMT
CMD ["telegraf"]
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
	-	`sha256:3c5e13aa4be9211a1b0511b6920b59ea9f46d7c0689e7d23d966e2fa3959ef24`  
		Last Modified: Fri, 02 Jun 2017 17:30:38 GMT  
		Size: 4.7 MB (4705680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec76e021997cff53c7c748e501851968bb34d36c7755514396a414ce0277d800`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 6.9 KB (6881 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d41fc9c6b408bb335e7c78c70606c4804bec48745d2ac10edae0dc7d4d3f912`  
		Last Modified: Sat, 03 Jun 2017 05:02:22 GMT  
		Size: 11.5 MB (11547569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84cfe5c2545194eaf0e4148081539a9ed739d1f0fd40962e68de73dfa47bfd2d`  
		Last Modified: Sat, 03 Jun 2017 05:02:20 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.3.1`

```console
$ docker pull telegraf@sha256:ada005b2e652e50a34338b006f8147095ac9d9f65429070f1e72862d006f3faf
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.3.1` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83444325 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bd66ca8c5f5864eac119c161721df7364040e41689b5fa5725600a6c155c24e5`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

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
# Fri, 02 Jun 2017 17:07:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 04:59:30 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Sat, 03 Jun 2017 05:00:06 GMT
ENV TELEGRAF_VERSION=1.3.1
# Sat, 03 Jun 2017 05:00:10 GMT
RUN wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}-1_amd64.deb.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     gpg --batch --verify telegraf_${TELEGRAF_VERSION}-1_amd64.deb.asc telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     dpkg -i telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     rm -f telegraf_${TELEGRAF_VERSION}-1_amd64.deb*
# Sat, 03 Jun 2017 05:00:11 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Sat, 03 Jun 2017 05:00:12 GMT
COPY file:7211de01f296351833389a1a1879d450e2cb727d7e2910d5807937f99983edf7 in /entrypoint.sh 
# Sat, 03 Jun 2017 05:00:13 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 03 Jun 2017 05:00:14 GMT
CMD ["telegraf"]
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
	-	`sha256:3c5e13aa4be9211a1b0511b6920b59ea9f46d7c0689e7d23d966e2fa3959ef24`  
		Last Modified: Fri, 02 Jun 2017 17:30:38 GMT  
		Size: 4.7 MB (4705680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec76e021997cff53c7c748e501851968bb34d36c7755514396a414ce0277d800`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 6.9 KB (6881 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d41fc9c6b408bb335e7c78c70606c4804bec48745d2ac10edae0dc7d4d3f912`  
		Last Modified: Sat, 03 Jun 2017 05:02:22 GMT  
		Size: 11.5 MB (11547569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84cfe5c2545194eaf0e4148081539a9ed739d1f0fd40962e68de73dfa47bfd2d`  
		Last Modified: Sat, 03 Jun 2017 05:02:20 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:latest`

```console
$ docker pull telegraf@sha256:ada005b2e652e50a34338b006f8147095ac9d9f65429070f1e72862d006f3faf
```

-	Platforms:
	-	linux; amd64

### `telegraf:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **83.4 MB (83444325 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bd66ca8c5f5864eac119c161721df7364040e41689b5fa5725600a6c155c24e5`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

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
# Fri, 02 Jun 2017 17:07:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 04:59:30 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Sat, 03 Jun 2017 05:00:06 GMT
ENV TELEGRAF_VERSION=1.3.1
# Sat, 03 Jun 2017 05:00:10 GMT
RUN wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}-1_amd64.deb.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     gpg --batch --verify telegraf_${TELEGRAF_VERSION}-1_amd64.deb.asc telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     dpkg -i telegraf_${TELEGRAF_VERSION}-1_amd64.deb &&     rm -f telegraf_${TELEGRAF_VERSION}-1_amd64.deb*
# Sat, 03 Jun 2017 05:00:11 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Sat, 03 Jun 2017 05:00:12 GMT
COPY file:7211de01f296351833389a1a1879d450e2cb727d7e2910d5807937f99983edf7 in /entrypoint.sh 
# Sat, 03 Jun 2017 05:00:13 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 03 Jun 2017 05:00:14 GMT
CMD ["telegraf"]
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
	-	`sha256:3c5e13aa4be9211a1b0511b6920b59ea9f46d7c0689e7d23d966e2fa3959ef24`  
		Last Modified: Fri, 02 Jun 2017 17:30:38 GMT  
		Size: 4.7 MB (4705680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec76e021997cff53c7c748e501851968bb34d36c7755514396a414ce0277d800`  
		Last Modified: Sat, 03 Jun 2017 05:00:40 GMT  
		Size: 6.9 KB (6881 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d41fc9c6b408bb335e7c78c70606c4804bec48745d2ac10edae0dc7d4d3f912`  
		Last Modified: Sat, 03 Jun 2017 05:02:22 GMT  
		Size: 11.5 MB (11547569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84cfe5c2545194eaf0e4148081539a9ed739d1f0fd40962e68de73dfa47bfd2d`  
		Last Modified: Sat, 03 Jun 2017 05:02:20 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.3-alpine`

```console
$ docker pull telegraf@sha256:d05c710b7d3265f76cf04b76dc223ba3a5dd436c33995be4f8173de64e4f907d
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.3-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **10.9 MB (10925327 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4c137a971dfccbd22de20177f8d12a5b70362a9ba15b0fc4c38076c10bd8be2b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Thu, 25 May 2017 23:32:38 GMT
ADD file:df15515197b183747a0b7ccefd75973edc87fc7a5bce30fa10ae94e75928d25c in / 
# Thu, 25 May 2017 23:32:38 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 16:29:15 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Thu, 01 Jun 2017 23:56:17 GMT
RUN apk add --no-cache iputils ca-certificates &&     update-ca-certificates
# Thu, 01 Jun 2017 23:58:55 GMT
ENV TELEGRAF_VERSION=1.3.1
# Thu, 01 Jun 2017 23:59:04 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Thu, 01 Jun 2017 23:59:05 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Thu, 01 Jun 2017 23:59:06 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Thu, 01 Jun 2017 23:59:06 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 01 Jun 2017 23:59:07 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:6f821164d5b7ec94868795c1fb8dc6fd7d1fe51e04f97a6cf3a487868f2f5d68`  
		Last Modified: Thu, 25 May 2017 23:36:24 GMT  
		Size: 2.0 MB (1967927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fb7a10a08f9c25306f2f520f46b33d97a83c5a4138ad35810dad882d0982231`  
		Last Modified: Tue, 30 May 2017 16:30:02 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46f61cc0c7d37271f541554621a5e0adf8f74f958cf4a865c0473ed60a6b3138`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 447.4 KB (447402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:52911f537e68c6cbf3368784306e1dfa4872f4efec5d63b601045ef8807f222f`  
		Last Modified: Fri, 02 Jun 2017 00:02:29 GMT  
		Size: 8.5 MB (8509661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8156478d55e5c23e6e954bcfe1750c21228ecc3998538601f4b0f82cb70a89eb`  
		Last Modified: Fri, 02 Jun 2017 00:02:28 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:1.3.1-alpine`

```console
$ docker pull telegraf@sha256:d05c710b7d3265f76cf04b76dc223ba3a5dd436c33995be4f8173de64e4f907d
```

-	Platforms:
	-	linux; amd64

### `telegraf:1.3.1-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **10.9 MB (10925327 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4c137a971dfccbd22de20177f8d12a5b70362a9ba15b0fc4c38076c10bd8be2b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Thu, 25 May 2017 23:32:38 GMT
ADD file:df15515197b183747a0b7ccefd75973edc87fc7a5bce30fa10ae94e75928d25c in / 
# Thu, 25 May 2017 23:32:38 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 16:29:15 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Thu, 01 Jun 2017 23:56:17 GMT
RUN apk add --no-cache iputils ca-certificates &&     update-ca-certificates
# Thu, 01 Jun 2017 23:58:55 GMT
ENV TELEGRAF_VERSION=1.3.1
# Thu, 01 Jun 2017 23:59:04 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Thu, 01 Jun 2017 23:59:05 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Thu, 01 Jun 2017 23:59:06 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Thu, 01 Jun 2017 23:59:06 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 01 Jun 2017 23:59:07 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:6f821164d5b7ec94868795c1fb8dc6fd7d1fe51e04f97a6cf3a487868f2f5d68`  
		Last Modified: Thu, 25 May 2017 23:36:24 GMT  
		Size: 2.0 MB (1967927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fb7a10a08f9c25306f2f520f46b33d97a83c5a4138ad35810dad882d0982231`  
		Last Modified: Tue, 30 May 2017 16:30:02 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46f61cc0c7d37271f541554621a5e0adf8f74f958cf4a865c0473ed60a6b3138`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 447.4 KB (447402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:52911f537e68c6cbf3368784306e1dfa4872f4efec5d63b601045ef8807f222f`  
		Last Modified: Fri, 02 Jun 2017 00:02:29 GMT  
		Size: 8.5 MB (8509661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8156478d55e5c23e6e954bcfe1750c21228ecc3998538601f4b0f82cb70a89eb`  
		Last Modified: Fri, 02 Jun 2017 00:02:28 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `telegraf:alpine`

```console
$ docker pull telegraf@sha256:d05c710b7d3265f76cf04b76dc223ba3a5dd436c33995be4f8173de64e4f907d
```

-	Platforms:
	-	linux; amd64

### `telegraf:alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **10.9 MB (10925327 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4c137a971dfccbd22de20177f8d12a5b70362a9ba15b0fc4c38076c10bd8be2b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Thu, 25 May 2017 23:32:38 GMT
ADD file:df15515197b183747a0b7ccefd75973edc87fc7a5bce30fa10ae94e75928d25c in / 
# Thu, 25 May 2017 23:32:38 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 16:29:15 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Thu, 01 Jun 2017 23:56:17 GMT
RUN apk add --no-cache iputils ca-certificates &&     update-ca-certificates
# Thu, 01 Jun 2017 23:58:55 GMT
ENV TELEGRAF_VERSION=1.3.1
# Thu, 01 Jun 2017 23:59:04 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Thu, 01 Jun 2017 23:59:05 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Thu, 01 Jun 2017 23:59:06 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Thu, 01 Jun 2017 23:59:06 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 01 Jun 2017 23:59:07 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:6f821164d5b7ec94868795c1fb8dc6fd7d1fe51e04f97a6cf3a487868f2f5d68`  
		Last Modified: Thu, 25 May 2017 23:36:24 GMT  
		Size: 2.0 MB (1967927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fb7a10a08f9c25306f2f520f46b33d97a83c5a4138ad35810dad882d0982231`  
		Last Modified: Tue, 30 May 2017 16:30:02 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46f61cc0c7d37271f541554621a5e0adf8f74f958cf4a865c0473ed60a6b3138`  
		Last Modified: Fri, 02 Jun 2017 00:00:19 GMT  
		Size: 447.4 KB (447402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:52911f537e68c6cbf3368784306e1dfa4872f4efec5d63b601045ef8807f222f`  
		Last Modified: Fri, 02 Jun 2017 00:02:29 GMT  
		Size: 8.5 MB (8509661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8156478d55e5c23e6e954bcfe1750c21228ecc3998538601f4b0f82cb70a89eb`  
		Last Modified: Fri, 02 Jun 2017 00:02:28 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
