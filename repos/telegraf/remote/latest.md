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
