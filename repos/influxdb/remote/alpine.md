## `influxdb:alpine`

```console
$ docker pull influxdb@sha256:f2ce05a039b67b6c4fd2b028ffeecad54fd7cb6137111e314c6079571a863b4c
```

-	Platforms:
	-	linux; amd64

### `influxdb:alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.4 MB (14398907 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f5b1ac29498d0f23523ea1156d1b4826f4a99efda1d6992ca05c68ed72742c0e`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["influxd"]`

```dockerfile
# Thu, 25 May 2017 23:32:38 GMT
ADD file:df15515197b183747a0b7ccefd75973edc87fc7a5bce30fa10ae94e75928d25c in / 
# Thu, 25 May 2017 23:32:38 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 16:29:15 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Tue, 30 May 2017 20:28:15 GMT
ENV INFLUXDB_VERSION=1.2.4
# Tue, 30 May 2017 20:28:23 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar ca-certificates &&     update-ca-certificates &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz.asc influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src &&     tar -C /usr/src -xzf influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     rm -f /usr/src/influxdb-*/influxdb.conf &&     chmod +x /usr/src/influxdb-*/* &&     cp -a /usr/src/influxdb-*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Tue, 30 May 2017 20:29:00 GMT
COPY file:3ee2bc0321c2aa2451df7a508649c3a54f0eebc1ef9b8a24967c58105b4d3160 in /etc/influxdb/influxdb.conf 
# Tue, 30 May 2017 20:29:23 GMT
EXPOSE 8086/tcp
# Tue, 30 May 2017 20:29:24 GMT
VOLUME [/var/lib/influxdb]
# Tue, 30 May 2017 20:29:25 GMT
COPY file:69ba622c5d14acee69909e208de64bf13aa81f0010ff82238c8825ba99d65290 in /entrypoint.sh 
# Tue, 30 May 2017 20:29:26 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 30 May 2017 20:29:48 GMT
CMD ["influxd"]
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
	-	`sha256:bdf5fe8a5c60c9f98a05d2e0fa6ea5c70e9d8d46e19a3c60716509353556e09a`  
		Last Modified: Tue, 30 May 2017 20:32:03 GMT  
		Size: 12.4 MB (12430418 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:979951357ac6b75d8d03f6eb6eee0ec0a7c089f02cd46e003034c34fe5cc5d68`  
		Last Modified: Tue, 30 May 2017 20:32:00 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c50f812d262418edd397bfc0af2167ba17c02237e9108b389ebd0283265dbfd`  
		Last Modified: Tue, 30 May 2017 20:32:00 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
