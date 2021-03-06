## `traefik:raclette`

```console
$ docker pull traefik@sha256:e138501b457d2f5f5a9b22e11a2c558939308867b67310a127665e4aa4de09e0
```

-	Platforms:
	-	linux; amd64

### `traefik:raclette` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.0 MB (12967476 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:945164403d33f554dd2778bf21d48f15959590ac6c79922622fc108ec30eb1f3`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Thu, 15 Dec 2016 17:54:02 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Wed, 31 May 2017 19:29:47 GMT
COPY file:436e5eecb4f0e9138c64fe18e235611f9daa603405803d5f98a8a595ff925123 in / 
# Wed, 31 May 2017 19:29:48 GMT
EXPOSE 80/tcp
# Wed, 31 May 2017 19:29:50 GMT
ENTRYPOINT ["/traefik"]
# Wed, 31 May 2017 19:29:51 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.3.0 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:03a84e30597f6e498aa09e940b69f623d31c22909fa05c7132e1b142f9439e38`  
		Last Modified: Thu, 15 Dec 2016 17:54:23 GMT  
		Size: 156.1 KB (156143 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a78acefa147927cf2d2d064b416f542041b8464e0f3de193ea7771c0bade916`  
		Last Modified: Wed, 31 May 2017 19:31:14 GMT  
		Size: 12.8 MB (12811333 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
