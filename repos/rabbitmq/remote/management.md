## `rabbitmq:management`

```console
$ docker pull rabbitmq@sha256:86f8937de337a15b81cdf1bc7f75a078f5cf7ff0f359be95547a98113fe8bc08
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:management` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **88.0 MB (87958785 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:99d24cd4ff198d9aab19ec79089f59b5f19c74b56d2b73570cff674ccabd7fc3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 15:31:23 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 10 May 2017 15:31:24 GMT
ENV GOSU_VERSION=1.7
# Wed, 10 May 2017 15:31:43 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Wed, 10 May 2017 15:31:46 GMT
RUN set -ex; 	key='434975BD900CCBE4F7EE1B1ED208507CA14F4FCA'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/erlang-solutions.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 10 May 2017 15:31:48 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Wed, 10 May 2017 15:32:19 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:32:20 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 10 May 2017 15:32:23 GMT
RUN set -ex; 	key='0A9AF2115F4687BD29803A206B73A36E6026DFCA'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/rabbitmq.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 10 May 2017 15:32:24 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Tue, 30 May 2017 17:32:18 GMT
ENV RABBITMQ_VERSION=3.6.10
# Tue, 30 May 2017 17:32:20 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.10-1
# Tue, 30 May 2017 17:32:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Tue, 30 May 2017 17:33:12 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 30 May 2017 17:33:13 GMT
ENV HOME=/var/lib/rabbitmq
# Tue, 30 May 2017 17:33:37 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Tue, 30 May 2017 17:33:59 GMT
VOLUME [/var/lib/rabbitmq]
# Tue, 30 May 2017 17:34:02 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Tue, 30 May 2017 17:34:27 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Sat, 03 Jun 2017 19:05:49 GMT
COPY file:95ed14b1f44e48ff624503df658f6073cc490c98fb19105180ea52d93812a81d in /usr/local/bin/ 
# Sat, 03 Jun 2017 19:05:51 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 03 Jun 2017 19:05:52 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 03 Jun 2017 19:05:53 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Sat, 03 Jun 2017 19:05:53 GMT
CMD ["rabbitmq-server"]
# Sat, 03 Jun 2017 19:06:19 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Sat, 03 Jun 2017 19:06:20 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ad3529559716ef2226d04b49688e86c4e33e25788838dce402a97e3b9cb4357`  
		Last Modified: Sat, 13 May 2017 18:07:30 GMT  
		Size: 4.4 KB (4376 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8d6f7fd21c4b2507908ced40197cca24acbeaf097f52fa31a0f88b63830d7f4`  
		Last Modified: Sat, 13 May 2017 18:07:30 GMT  
		Size: 1.3 MB (1307776 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4971849d324fe6ca2ba0aef4418bb06d9999a0bf90527f86ba6e916ff0bbd2bc`  
		Last Modified: Sat, 13 May 2017 18:07:28 GMT  
		Size: 2.5 KB (2502 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c4afa2fcab88b38bb66b17fb0162c5a7d5175984afd079022afdc6a65f18acd`  
		Last Modified: Sat, 13 May 2017 18:07:28 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a846993595cb3919b6d37f55dc1e1ac7f593a8ff7dd58d3f2d03dc64e8a2d43`  
		Last Modified: Sat, 13 May 2017 18:07:32 GMT  
		Size: 28.3 MB (28347945 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:afe1747cbdec723d9f40051e657d28358e6a09f751ccb1a2ea807a44f27d5e8d`  
		Last Modified: Sat, 13 May 2017 18:07:27 GMT  
		Size: 3.1 KB (3099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4773d4648f681e6de65dddf61ca22be624193850b6d76a93ee78f0305926dca`  
		Last Modified: Sat, 13 May 2017 18:07:27 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0b37a62317bf84e750f03fbee37fd1f8de5b3c8743819e11cbb9194b4b854c6`  
		Last Modified: Tue, 30 May 2017 17:59:54 GMT  
		Size: 5.7 MB (5701762 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa3dbc4804b4a7f4fa3d0e3845bde7884071c891863a1454956c82b82712f71d`  
		Last Modified: Tue, 30 May 2017 17:59:52 GMT  
		Size: 2.2 KB (2232 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a35f964b5a125f4382c6760b7b97f7759ee5e7382d2a0ce37c0654742a48cfbd`  
		Last Modified: Tue, 30 May 2017 17:59:52 GMT  
		Size: 147.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19c4ee3f7947026382b407186174011eea0e49b7e7ea7d9a95570a7144d4ccf6`  
		Last Modified: Tue, 30 May 2017 17:59:52 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5aa9a1a1633aee86de3570e269e0fdf6c0f5bbd57d76fc54508aad87f87cb3fd`  
		Last Modified: Sat, 03 Jun 2017 19:07:39 GMT  
		Size: 4.1 KB (4058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88df8c4db0e8c44df3314406580778696cbe1711ec0c109b647a3234d3be4b06`  
		Last Modified: Sat, 03 Jun 2017 19:07:39 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e2ed4134e5e61943960d385ae98faa975327bef4a7e81722150cf84acd2572e`  
		Last Modified: Sat, 03 Jun 2017 19:09:21 GMT  
		Size: 187.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
