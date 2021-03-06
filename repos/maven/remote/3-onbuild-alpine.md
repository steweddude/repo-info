## `maven:3-onbuild-alpine`

```console
$ docker pull maven@sha256:1163c0720e26e4cb3f5635f913f31a0171a6493cf7927c176bd5609c0972cdc3
```

-	Platforms:
	-	linux; amd64

### `maven:3-onbuild-alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **82.4 MB (82374677 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2cdf277912a0e8ec669810af84c8cc47a51ac3a0b0ff7c087e487b1f9f9c457c`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

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
# Thu, 11 May 2017 05:14:48 GMT
RUN apk add --no-cache curl tar bash
# Thu, 11 May 2017 05:14:49 GMT
ARG MAVEN_VERSION=3.5.0
# Thu, 11 May 2017 05:14:49 GMT
ARG USER_HOME_DIR=/root
# Thu, 11 May 2017 05:14:50 GMT
ARG SHA=beb91419245395bd69a4a6edad5ca3ec1a8b64e41457672dc687c173a495f034
# Thu, 11 May 2017 05:14:51 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.0/binaries
# Thu, 11 May 2017 05:14:54 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.0/binaries MAVEN_VERSION=3.5.0 SHA=beb91419245395bd69a4a6edad5ca3ec1a8b64e41457672dc687c173a495f034 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-$MAVEN_VERSION-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 11 May 2017 05:14:54 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 11 May 2017 05:14:55 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 11 May 2017 05:14:56 GMT
COPY file:0ef06202c434fd6422eaf47010435819a589a77ab2d8d5d3b9e497de2fd57b3f in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 11 May 2017 05:14:57 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 11 May 2017 05:14:58 GMT
VOLUME [/root/.m2]
# Thu, 11 May 2017 05:14:59 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 11 May 2017 05:15:00 GMT
CMD ["mvn"]
# Thu, 11 May 2017 05:17:40 GMT
RUN mkdir -p /usr/src/app
# Thu, 11 May 2017 05:17:41 GMT
WORKDIR /usr/src/app
# Thu, 11 May 2017 05:17:42 GMT
ONBUILD ADD . /usr/src/app
# Thu, 11 May 2017 05:17:43 GMT
ONBUILD RUN mvn install
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
	-	`sha256:b90eb3991a51dce61c3e6b2080b4afa57bba3cc5074a31911a867483a8daa360`  
		Last Modified: Sat, 13 May 2017 17:10:53 GMT  
		Size: 1.7 MB (1728409 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79eb66973f0d559344715a6f95e0e9dfa4b59fc5755c133507d395e1d5c2ed5a`  
		Last Modified: Sat, 13 May 2017 17:10:54 GMT  
		Size: 8.7 MB (8672760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:86c82c2e3ac8fc2d32ace00d04b06afa2d2be50df39102d2071b4316da59b770`  
		Last Modified: Sat, 13 May 2017 17:10:51 GMT  
		Size: 713.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f88dfad34afac4fccf4b9b1dfa5ccc3e1218a8e450effab396748a6f4271babe`  
		Last Modified: Sat, 13 May 2017 17:10:51 GMT  
		Size: 350.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa1586ea2d3bf4dda7bcceacb6ccb58bf5e435155100a347192c5687023dcf93`  
		Last Modified: Sat, 13 May 2017 17:16:09 GMT  
		Size: 160.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
