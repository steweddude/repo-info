## `jenkins:latest`

```console
$ docker pull jenkins@sha256:0e2b101c8802d0ef2de411e9b9b78a5c4403635d96210ab52ada882cea646369
```

-	Platforms:
	-	linux; amd64

### `jenkins:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **317.2 MB (317205498 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:59b08e8f6e37951d7d3b95b7c29d4285dba579f7f3111204e85d99633d929985`
-	Entrypoint: `["\/bin\/tini","--","\/usr\/local\/bin\/jenkins.sh"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Mon, 08 May 2017 23:53:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 08 May 2017 23:54:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 13:56:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 13:58:58 GMT
RUN echo 'deb http://deb.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Wed, 10 May 2017 13:58:59 GMT
ENV LANG=C.UTF-8
# Wed, 10 May 2017 13:59:00 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 10 May 2017 13:59:02 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 10 May 2017 13:59:03 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 16 May 2017 17:24:35 GMT
ENV JAVA_VERSION=8u131
# Tue, 16 May 2017 17:24:36 GMT
ENV JAVA_DEBIAN_VERSION=8u131-b11-1~bpo8+1
# Tue, 16 May 2017 17:24:37 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20161107~bpo8+1
# Tue, 16 May 2017 17:25:28 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y 		openjdk-8-jdk="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 16 May 2017 17:25:34 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 16 May 2017 21:55:22 GMT
RUN apt-get update && apt-get install -y git curl && rm -rf /var/lib/apt/lists/*
# Tue, 16 May 2017 21:55:23 GMT
ENV JENKINS_HOME=/var/jenkins_home
# Tue, 16 May 2017 21:55:24 GMT
ENV JENKINS_SLAVE_AGENT_PORT=50000
# Tue, 16 May 2017 21:55:25 GMT
ARG user=jenkins
# Tue, 16 May 2017 21:55:25 GMT
ARG group=jenkins
# Tue, 16 May 2017 21:55:26 GMT
ARG uid=1000
# Tue, 16 May 2017 21:55:27 GMT
ARG gid=1000
# Tue, 16 May 2017 21:55:28 GMT
# ARGS: gid=1000 group=jenkins uid=1000 user=jenkins
RUN groupadd -g ${gid} ${group}     && useradd -d "$JENKINS_HOME" -u ${uid} -g ${gid} -m -s /bin/bash ${user}
# Tue, 16 May 2017 21:55:29 GMT
VOLUME [/var/jenkins_home]
# Tue, 16 May 2017 21:55:31 GMT
# ARGS: gid=1000 group=jenkins uid=1000 user=jenkins
RUN mkdir -p /usr/share/jenkins/ref/init.groovy.d
# Tue, 16 May 2017 21:55:32 GMT
ENV TINI_VERSION=0.14.0
# Tue, 16 May 2017 21:55:33 GMT
ENV TINI_SHA=6c41ec7d33e857d4779f14d9c74924cab0c7973485d2972419a3b7c7620ff5fd
# Tue, 16 May 2017 21:55:36 GMT
# ARGS: gid=1000 group=jenkins uid=1000 user=jenkins
RUN curl -fsSL https://github.com/krallin/tini/releases/download/v${TINI_VERSION}/tini-static-amd64 -o /bin/tini && chmod +x /bin/tini   && echo "$TINI_SHA  /bin/tini" | sha256sum -c -
# Tue, 16 May 2017 21:55:38 GMT
COPY file:c629bc0b9ecb5b7233000c973f65721df4ce1307a5d5b33ac3871ff61a9172ff in /usr/share/jenkins/ref/init.groovy.d/tcp-slave-agent-port.groovy 
# Tue, 16 May 2017 21:55:39 GMT
ARG JENKINS_VERSION
# Fri, 26 May 2017 14:31:40 GMT
ENV JENKINS_VERSION=2.46.3
# Fri, 26 May 2017 14:31:41 GMT
ARG JENKINS_SHA=00424d3c851298b29376d1d09d7d3578a2bc4a03acf3914b317c47707cd5739a
# Fri, 26 May 2017 14:31:42 GMT
ARG JENKINS_URL=https://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/2.46.3/jenkins-war-2.46.3.war
# Fri, 26 May 2017 14:31:50 GMT
# ARGS: JENKINS_SHA=00424d3c851298b29376d1d09d7d3578a2bc4a03acf3914b317c47707cd5739a JENKINS_URL=https://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/2.46.3/jenkins-war-2.46.3.war gid=1000 group=jenkins uid=1000 user=jenkins
RUN curl -fsSL ${JENKINS_URL} -o /usr/share/jenkins/jenkins.war   && echo "${JENKINS_SHA}  /usr/share/jenkins/jenkins.war" | sha256sum -c -
# Fri, 26 May 2017 14:31:51 GMT
ENV JENKINS_UC=https://updates.jenkins.io
# Fri, 26 May 2017 14:31:52 GMT
# ARGS: JENKINS_SHA=00424d3c851298b29376d1d09d7d3578a2bc4a03acf3914b317c47707cd5739a JENKINS_URL=https://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/2.46.3/jenkins-war-2.46.3.war gid=1000 group=jenkins uid=1000 user=jenkins
RUN chown -R ${user} "$JENKINS_HOME" /usr/share/jenkins/ref
# Fri, 26 May 2017 14:31:53 GMT
EXPOSE 8080/tcp
# Fri, 26 May 2017 14:31:54 GMT
EXPOSE 50000/tcp
# Fri, 26 May 2017 14:31:55 GMT
ENV COPY_REFERENCE_FILE_LOG=/var/jenkins_home/copy_reference_file.log
# Fri, 26 May 2017 14:31:56 GMT
USER [jenkins]
# Fri, 26 May 2017 14:31:58 GMT
COPY file:26c3c5818bc87662d1f4905a3ed73bd55a0a75f731c7dc52d0599c00f51408e9 in /usr/local/bin/jenkins-support 
# Fri, 26 May 2017 14:31:59 GMT
COPY file:7eec179a0dd3aad4a9c9290bc4d85e4775c8cf6bc2932527892ca6e87739e474 in /usr/local/bin/jenkins.sh 
# Fri, 26 May 2017 14:32:00 GMT
ENTRYPOINT ["/bin/tini" "--" "/usr/local/bin/jenkins.sh"]
# Fri, 26 May 2017 14:32:01 GMT
COPY file:93fb511d485dd2d6060c484dcedb902947875042048de529676a0a0aed27b5a3 in /usr/local/bin/plugins.sh 
# Fri, 26 May 2017 14:32:03 GMT
COPY file:2a6a3e16202b8dddab5edef50f712c16fe8f6980f5aea80c8c76b5db4f903913 in /usr/local/bin/install-plugins.sh 
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb5937da9414eeab6d68ce06a7ff60d8be1e2c1518ac2588d5df135ab54a9801`  
		Last Modified: Tue, 09 May 2017 15:55:04 GMT  
		Size: 19.3 MB (19267434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9021b2326a1e3a942223c7e349a92203df184f2dcca45f5be7b0b80ac50e2ccf`  
		Last Modified: Tue, 09 May 2017 15:56:09 GMT  
		Size: 43.2 MB (43230898 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c6c40e9ec4f6391c64835fdca6e24f30e94cf00167fcab85f7924edd28e8dc3`  
		Last Modified: Fri, 12 May 2017 15:06:38 GMT  
		Size: 599.4 KB (599411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a63e1725461305af88d10e61a92787181321ad3d7b6136c7e48fe98feaf90ab`  
		Last Modified: Fri, 12 May 2017 15:13:10 GMT  
		Size: 216.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79e8ed83f43abdbf634120e74208a01288910381bfe3390fa76cd64ec0e17891`  
		Last Modified: Fri, 12 May 2017 15:13:08 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:161cbb85a481fc9402d5916ebf18e88d992e4d149ddd1ac4f5580757a84ace19`  
		Last Modified: Fri, 12 May 2017 15:13:08 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a479609da9c84ce06a53830a9b6da0725422474002ffc30a574ed0fbc5efca86`  
		Last Modified: Tue, 16 May 2017 17:39:22 GMT  
		Size: 119.4 MB (119353660 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e32f81724ea45927d432793e3a33fadc213949aaa5a35217f9fc9ac6e147c8b3`  
		Last Modified: Tue, 16 May 2017 17:39:07 GMT  
		Size: 289.7 KB (289652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01f94cc7c7609446b3f79a2076585a511783301a9388bed09e70d4c88292627c`  
		Last Modified: Tue, 16 May 2017 21:57:14 GMT  
		Size: 11.4 MB (11383753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eaab3977dfc10c54fd0e83b55946be5cf43694a0122e98c8ac529e64f8b53996`  
		Last Modified: Tue, 16 May 2017 21:57:11 GMT  
		Size: 4.4 KB (4420 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea9c5bd17543c38fb23de098bd75c76055f9c9b08f38c449258c280068a56d32`  
		Last Modified: Tue, 16 May 2017 21:57:11 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d4dea85f623c34e319cd9089a8e6f6fa288bd8a21a22f05f819bfa22bdf1562`  
		Last Modified: Tue, 16 May 2017 21:57:11 GMT  
		Size: 354.8 KB (354776 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92b5ef9808537e446d086a459f12fc37da58fb03fe7573d7bbe77f0c31074af5`  
		Last Modified: Tue, 16 May 2017 21:57:11 GMT  
		Size: 421.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df54c33bed24fad6b9dc7f05126fd3bfdeedc8c075f12c80c5e5c30643b139d3`  
		Last Modified: Fri, 26 May 2017 14:33:17 GMT  
		Size: 70.1 MB (70129896 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:115a9ce3739e2d6e27d4a91144d1c7e29bd1b5ce3b9583f1865fd2f1f3a2756f`  
		Last Modified: Fri, 26 May 2017 14:33:12 GMT  
		Size: 430.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82fb0b8c5d898d685fe6859ca66cc37b328f0cf728f20b58383b38118a32cc9d`  
		Last Modified: Fri, 26 May 2017 14:33:12 GMT  
		Size: 1.4 KB (1433 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9d8ee7cb2eddde473f2fd2208237147a247cd377affe4a2fbab0a52368f3ad2`  
		Last Modified: Fri, 26 May 2017 14:33:11 GMT  
		Size: 821.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8796fd84a6ed207922211568b9818bf8598f3511c908c3ad72e897c85178ec63`  
		Last Modified: Fri, 26 May 2017 14:33:12 GMT  
		Size: 1.5 KB (1528 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1573f34dbac2a939b0935d91445a1e283ed9939b03a611e6a3afdcfd996be70d`  
		Last Modified: Fri, 26 May 2017 14:33:11 GMT  
		Size: 2.2 KB (2187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
