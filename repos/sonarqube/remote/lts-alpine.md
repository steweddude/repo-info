## `sonarqube:lts-alpine`

```console
$ docker pull sonarqube@sha256:441a02144bc5c95e7fb28dd8a2d3965a98707894d9d0451059bb4ec480c6bc9b
```

-	Platforms:
	-	linux; amd64

### `sonarqube:lts-alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **193.7 MB (193698468 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:833edd0a146e77b7d0e6afd0b3a3bc96694e8ae3c6da28a72890f1454fb0a197`
-	Entrypoint: `[".\/bin\/run.sh"]`

```dockerfile
# Wed, 10 May 2017 16:38:16 GMT
ADD file:63f63606d6e289eb607c90e31de81802258906712727e473a2898f0f1ae55bb5 in / 
# Wed, 10 May 2017 16:38:17 GMT
CMD ["/bin/sh"]
# Wed, 10 May 2017 22:39:51 GMT
ENV LANG=C.UTF-8
# Wed, 10 May 2017 22:39:53 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 10 May 2017 22:39:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 10 May 2017 22:39:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 10 May 2017 22:39:55 GMT
ENV JAVA_VERSION=8u121
# Wed, 10 May 2017 22:39:56 GMT
ENV JAVA_ALPINE_VERSION=8.121.13-r0
# Wed, 10 May 2017 22:40:01 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 10 May 2017 23:14:54 GMT
MAINTAINER David Gageot <david.gageot@sonarsource.com>
# Wed, 10 May 2017 23:14:55 GMT
ENV SONAR_VERSION=5.6.6 SONARQUBE_HOME=/opt/sonarqube SONARQUBE_JDBC_USERNAME=sonar SONARQUBE_JDBC_PASSWORD=sonar SONARQUBE_JDBC_URL=
# Wed, 10 May 2017 23:14:55 GMT
EXPOSE 9000/tcp
# Wed, 10 May 2017 23:15:08 GMT
RUN set -x     && apk add --no-cache gnupg unzip     && apk add --no-cache libressl wget     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys F1182E81C792928921DBCAB4CFCA4A29D26468DE     && mkdir /opt     && cd /opt     && wget -O sonarqube.zip --no-verbose https://sonarsource.bintray.com/Distribution/sonarqube/sonarqube-$SONAR_VERSION.zip     && wget -O sonarqube.zip.asc --no-verbose https://sonarsource.bintray.com/Distribution/sonarqube/sonarqube-$SONAR_VERSION.zip.asc     && gpg --batch --verify sonarqube.zip.asc sonarqube.zip     && unzip sonarqube.zip     && mv sonarqube-$SONAR_VERSION sonarqube     && rm sonarqube.zip*     && rm -rf $SONARQUBE_HOME/bin/*
# Wed, 10 May 2017 23:15:09 GMT
VOLUME [/opt/sonarqube/data]
# Wed, 10 May 2017 23:15:10 GMT
WORKDIR /opt/sonarqube
# Wed, 10 May 2017 23:15:11 GMT
COPY file:83e169627dc34c4308fd222d47a1ae7c388a283efdc49980a885a8788308a052 in /opt/sonarqube/bin/ 
# Wed, 10 May 2017 23:15:12 GMT
ENTRYPOINT ["./bin/run.sh"]
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
	-	`sha256:b7d6497a92f9de7c9b828962ad09a648e1d72687dda6bb986a72e95c61bb3dad`  
		Last Modified: Fri, 12 May 2017 15:19:30 GMT  
		Size: 70.0 MB (70004148 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38524de4bb8d766d67606d0c4c09e3c16cf4695cf47c68d29b65c22a572e3869`  
		Last Modified: Sat, 13 May 2017 18:56:51 GMT  
		Size: 121.7 MB (121725751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb4e9926c99d5f58c30646531737eb6c0bad64b8c66cc1a31e348b939fb12c77`  
		Last Modified: Sat, 13 May 2017 18:56:40 GMT  
		Size: 432.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
