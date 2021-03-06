## `vault:latest`

```console
$ docker pull vault@sha256:c2850027c6c3bf9ec3fd14ec7fa30e6b9449774bd17f64beda71e38643846c95
```

-	Platforms:
	-	linux; amd64

### `vault:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **18.4 MB (18433108 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c02739da78bb63569ca2e78eecaeec7abd8885b79ab9c7ed439c91b960b44b01`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["server","-dev"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Wed, 10 May 2017 23:39:28 GMT
MAINTAINER Jeff Mitchell <jeff@hashicorp.com> (@jefferai)
# Thu, 18 May 2017 17:24:01 GMT
ENV VAULT_VERSION=0.7.2
# Thu, 18 May 2017 17:24:02 GMT
ENV DOCKER_BASE_VERSION=0.0.4
# Thu, 18 May 2017 17:24:03 GMT
RUN addgroup vault &&     adduser -S -G vault vault
# Thu, 18 May 2017 17:24:13 GMT
RUN apk add --no-cache ca-certificates gnupg openssl libcap jq &&     gpg --recv-keys 91A6E7F85D05C65630BEF18951852D87348FFC4C &&     mkdir -p /tmp/build &&     cd /tmp/build &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     grep ${DOCKER_BASE_VERSION}_linux_amd64.zip docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS | sha256sum -c &&     unzip docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     cp bin/gosu bin/dumb-init /bin &&     wget https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_linux_amd64.zip &&     wget https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_SHA256SUMS &&     wget https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify vault_${VAULT_VERSION}_SHA256SUMS.sig vault_${VAULT_VERSION}_SHA256SUMS &&     grep vault_${VAULT_VERSION}_linux_amd64.zip vault_${VAULT_VERSION}_SHA256SUMS | sha256sum -c &&     unzip -d /bin vault_${VAULT_VERSION}_linux_amd64.zip &&     cd /tmp &&     rm -rf /tmp/build &&     apk del gnupg openssl &&     rm -rf /root/.gnupg
# Thu, 18 May 2017 17:24:14 GMT
RUN mkdir -p /vault/logs &&     mkdir -p /vault/file &&     mkdir -p /vault/config &&     chown -R vault:vault /vault
# Thu, 18 May 2017 17:24:15 GMT
VOLUME [/vault/logs]
# Thu, 18 May 2017 17:24:16 GMT
VOLUME [/vault/file]
# Thu, 18 May 2017 17:24:16 GMT
EXPOSE 8200/tcp
# Thu, 18 May 2017 17:24:17 GMT
COPY file:98bcd0ef55bd9ba781f5f486eef8d94bca7953eea74d785ef2b77818ebda7972 in /usr/local/bin/docker-entrypoint.sh 
# Thu, 18 May 2017 17:24:18 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 18 May 2017 17:24:19 GMT
CMD ["server" "-dev"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:164ef18e99e4d8d6b54e71aea847f8a5dc53f87e9cc182b98226c0316b140bc2`  
		Last Modified: Thu, 18 May 2017 17:25:51 GMT  
		Size: 1.3 KB (1278 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33a56227e9b5a782780b9279e794bed54824bad4ec75e0b1830c8a1718ae5b9a`  
		Last Modified: Thu, 18 May 2017 17:25:55 GMT  
		Size: 16.0 MB (16046873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:190e503cf9548def5421ac8d7154d0783008c314f064dad581e8f802135d1fe6`  
		Last Modified: Thu, 18 May 2017 17:25:51 GMT  
		Size: 154.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6388fb133802ead740a4c35155d33c0289f111ffb8211b373f4355bf2fe6f247`  
		Last Modified: Thu, 18 May 2017 17:25:51 GMT  
		Size: 1.8 KB (1766 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
