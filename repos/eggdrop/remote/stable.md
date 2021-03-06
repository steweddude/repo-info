## `eggdrop:stable`

```console
$ docker pull eggdrop@sha256:74a7d946f4cad5657e8249d227f3b07bd10169a5ecf86c407b49f60e6ec18fe4
```

-	Platforms:
	-	linux; amd64

### `eggdrop:stable` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **7.4 MB (7373343 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:507d67dfc618c9b5724f93a16a8339a7e0ca8999cb367df220a3145a4326426b`
-	Entrypoint: `["\/home\/eggdrop\/eggdrop\/entrypoint.sh"]`
-	Default Command: `["eggdrop.conf"]`

```dockerfile
# Thu, 25 May 2017 23:31:54 GMT
ADD file:c34582524a7c4fa2ccb67d48efaa6edacff8bc8115a26a511b2385a03f56aa8e in / 
# Thu, 25 May 2017 23:31:55 GMT
CMD ["/bin/sh"]
# Tue, 30 May 2017 17:20:26 GMT
MAINTAINER Geo Van O <geo@eggheads.org>
# Tue, 30 May 2017 17:20:28 GMT
RUN adduser -S eggdrop
# Tue, 30 May 2017 17:20:33 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Tue, 30 May 2017 17:26:39 GMT
RUN apk add --no-cache tcl tcl-dev wget ca-certificates make tar gpgme bash build-base openssl openssl-dev  && wget ftp://ftp.eggheads.org/pub/eggdrop/source/1.8/eggdrop-1.8.1.tar.gz   && wget ftp://ftp.eggheads.org/pub/eggdrop/source/1.8/eggdrop-1.8.1.tar.gz.asc   && gpg --keyserver ha.pool.sks-keyservers.net --recv-key E01C240484DE7DBE190FE141E7667DE1D1A39AFF   && gpg --batch --verify eggdrop-1.8.1.tar.gz.asc eggdrop-1.8.1.tar.gz   && rm eggdrop-1.8.1.tar.gz.asc   && tar -zxvf eggdrop-1.8.1.tar.gz   && rm eggdrop-1.8.1.tar.gz   && ( cd eggdrop-1.8.1     && ./configure     && make config     && make     && make install DEST=/home/eggdrop/eggdrop )   && rm -rf eggdrop-1.8.1   && mkdir /home/eggdrop/eggdrop/data   && chown -R eggdrop /home/eggdrop/eggdrop   && apk del tcl-dev wget ca-certificates make tar gpgme build-base openssl-dev
# Tue, 30 May 2017 17:26:54 GMT
ENV NICK=
# Tue, 30 May 2017 17:27:36 GMT
ENV SERVER=
# Tue, 30 May 2017 17:27:58 GMT
ENV LISTEN=3333
# Tue, 30 May 2017 17:27:59 GMT
ENV OWNER=
# Tue, 30 May 2017 17:28:24 GMT
ENV USERFILE=eggdrop.user
# Tue, 30 May 2017 17:28:26 GMT
ENV CHANFILE=eggdrop.chan
# Tue, 30 May 2017 17:28:28 GMT
WORKDIR /home/eggdrop/eggdrop
# Tue, 30 May 2017 17:28:56 GMT
EXPOSE 3333/tcp
# Tue, 30 May 2017 17:28:58 GMT
COPY file:7a054cb46364a47f244469cd44e0d12e9e0c49ab06cd99348b2a2bba3a4fb1c8 in /home/eggdrop/eggdrop 
# Tue, 30 May 2017 17:29:00 GMT
COPY file:919804e5ddd4c807c178caccfed03e9d75a459fe0f744c3a1ada109817cb44ec in /home/eggdrop/eggdrop/scripts/ 
# Tue, 30 May 2017 17:30:25 GMT
ENTRYPOINT ["/home/eggdrop/eggdrop/entrypoint.sh"]
# Tue, 30 May 2017 17:30:27 GMT
CMD ["eggdrop.conf"]
```

-	Layers:
	-	`sha256:486a8e636d6250a74d15cdb3582f4dd198271a80118f5a2f59de3d9cd8433611`  
		Last Modified: Thu, 25 May 2017 23:35:56 GMT  
		Size: 2.4 MB (2383064 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f8f6b69c917520b9ad10012ca08c1f11493d03ff995dc8c550ff402ff121be8`  
		Last Modified: Tue, 30 May 2017 17:35:24 GMT  
		Size: 1.3 KB (1278 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63213cd7e843857c542713817a6412b72b61def7f3debb504ea52586eb4ef198`  
		Last Modified: Tue, 30 May 2017 17:35:25 GMT  
		Size: 8.0 KB (8009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2994eefe3efa9bcbffaab52fbffc435ecd1e4549b1dda05c0aab650b1bccd95`  
		Last Modified: Tue, 30 May 2017 17:36:51 GMT  
		Size: 5.0 MB (4978559 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2bb93103866df09f1dfec3effe69e47370608a82a601a7d3d45531e47d0920cf`  
		Last Modified: Tue, 30 May 2017 17:36:48 GMT  
		Size: 1.7 KB (1739 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19823ebabae9963acb4803cd391259ebb3d2c26e6784898bc4336b0247cb48cb`  
		Last Modified: Tue, 30 May 2017 17:36:48 GMT  
		Size: 694.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
