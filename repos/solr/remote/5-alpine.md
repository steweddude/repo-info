## `solr:5-alpine`

```console
$ docker pull solr@sha256:f35085a3df77aa5f9498bfd3c8e6d3de1297ad764a9996ccb50dcf055300b740
```

-	Platforms:
	-	linux; amd64

### `solr:5-alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **194.1 MB (194107754 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f594cb9420bcc565d26633c371b4d88d0c9843ca76f9edb0c24961894db9e6f2`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Wed, 10 May 2017 16:38:16 GMT
ADD file:63f63606d6e289eb607c90e31de81802258906712727e473a2898f0f1ae55bb5 in / 
# Wed, 10 May 2017 16:38:17 GMT
CMD ["/bin/sh"]
# Wed, 10 May 2017 22:39:51 GMT
ENV LANG=C.UTF-8
# Wed, 10 May 2017 22:39:53 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 10 May 2017 22:40:21 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk/jre
# Wed, 10 May 2017 22:40:22 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 10 May 2017 22:40:22 GMT
ENV JAVA_VERSION=8u121
# Wed, 10 May 2017 22:40:23 GMT
ENV JAVA_ALPINE_VERSION=8.121.13-r0
# Wed, 10 May 2017 22:40:28 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 10 May 2017 23:11:30 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Wed, 10 May 2017 23:11:31 GMT
ARG SOLR_DOWNLOAD_SERVER
# Wed, 10 May 2017 23:11:34 GMT
RUN apk add --no-cache         lsof         gnupg         procps         tar         bash
# Wed, 10 May 2017 23:11:36 GMT
RUN apk add --no-cache ca-certificates wget &&         update-ca-certificates
# Wed, 10 May 2017 23:11:37 GMT
ENV SOLR_USER=solr
# Wed, 10 May 2017 23:11:37 GMT
ENV SOLR_UID=8983
# Wed, 10 May 2017 23:11:39 GMT
RUN addgroup -S -g $SOLR_UID $SOLR_USER &&   adduser -S -u $SOLR_UID -g $SOLR_USER $SOLR_USER
# Wed, 10 May 2017 23:11:39 GMT
ENV SOLR_VERSION=5.5.4
# Wed, 10 May 2017 23:11:40 GMT
ENV SOLR_URL=https://archive.apache.org/dist/lucene/solr/5.5.4/solr-5.5.4.tgz
# Wed, 10 May 2017 23:11:41 GMT
ENV SOLR_SHA256=c1528e4afc9a0b8e7e5be0a16f40bb4080f410d502cd63b4447d448c49e9f500
# Wed, 10 May 2017 23:11:41 GMT
ENV SOLR_KEYS=E6E21FFCDCEA14C95910EA65051A0FAF76BC6507
# Wed, 10 May 2017 23:11:45 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Wed, 10 May 2017 23:12:00 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -q $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -q $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores &&   sed -i -e 's/#SOLR_PORT=8983/SOLR_PORT=8983/' /opt/solr/bin/solr.in.sh &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_USER /opt/solr &&   mkdir /docker-entrypoint-initdb.d /opt/docker-solr/
# Wed, 10 May 2017 23:12:01 GMT
COPY dir:37fe27423809e9a020959b49d869a79285ab853758a6a8a6bfe8564dcdf7ff56 in /opt/docker-solr/scripts 
# Wed, 10 May 2017 23:12:03 GMT
RUN chown -R $SOLR_USER:$SOLR_USER /opt/docker-solr
# Wed, 10 May 2017 23:12:04 GMT
ENV PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 10 May 2017 23:12:04 GMT
EXPOSE 8983/tcp
# Wed, 10 May 2017 23:12:05 GMT
WORKDIR /opt/solr
# Wed, 10 May 2017 23:12:06 GMT
USER [solr]
# Wed, 10 May 2017 23:12:06 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 10 May 2017 23:12:07 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:cfc728c1c5584d8e0ae69368fc9c34d54d72651355573ba42554c2469a0a6299`  
		Last Modified: Wed, 10 May 2017 16:41:01 GMT  
		Size: 2.0 MB (1967906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b12b87f0a0e1bc0a163558cc56861b86355598153fb9e35273ece1dabe81cae`  
		Last Modified: Fri, 12 May 2017 15:19:23 GMT  
		Size: 231.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2361cda3c2da7cd65965703a6e97c9869536495a962105e26c948dd9a806e80d`  
		Last Modified: Fri, 12 May 2017 15:21:50 GMT  
		Size: 54.2 MB (54241012 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f086983660ec731d8cdd974f0ad2815a619a607a8a8593019fca87d6f60f061`  
		Last Modified: Sat, 13 May 2017 18:44:25 GMT  
		Size: 5.3 MB (5337882 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00105f936ad1b746bd483d43d62782245e001382192116167e57daeb98643a41`  
		Last Modified: Sat, 13 May 2017 18:44:20 GMT  
		Size: 619.4 KB (619414 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a110badf0266aa2c76ec5262f358e7b8fc1c45981da72b5abcf86aa341c8c9b`  
		Last Modified: Sat, 13 May 2017 18:44:22 GMT  
		Size: 1.2 KB (1244 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dcad6de034f1054a8b1acb9704293abb38e327cbac839d15d94f223d612e55cf`  
		Last Modified: Sat, 13 May 2017 18:44:20 GMT  
		Size: 7.1 KB (7096 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7ddc44bad2dd85dbce994192980c0d5b17ec312625d81b03a8c520547c7212c`  
		Last Modified: Sat, 13 May 2017 18:44:31 GMT  
		Size: 131.9 MB (131926934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14729d825c8663fe39b38ac69e1bef988a07b1c1ea4091a154a3dc879854b576`  
		Last Modified: Sat, 13 May 2017 18:44:20 GMT  
		Size: 3.0 KB (3012 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:654c2c45d645f2e9a4dc4273b8d3a15908a79fd84697358b29586af4e26c4f76`  
		Last Modified: Sat, 13 May 2017 18:44:20 GMT  
		Size: 3.0 KB (3023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
