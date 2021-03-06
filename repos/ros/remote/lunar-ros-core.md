## `ros:lunar-ros-core`

```console
$ docker pull ros@sha256:83cd2d08cae94b7a3d509d81e7c7e75a581d29da6b3b76be35fcff8bd91dbb78
```

-	Platforms:
	-	linux; amd64

### `ros:lunar-ros-core` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **299.5 MB (299488657 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1ca73c04a8832535cc281ce83fe0a5c2c16ffcc1d8b486e6e01952b7f215de72`
-	Entrypoint: `["\/ros_entrypoint.sh"]`
-	Default Command: `["bash"]`

```dockerfile
# Fri, 02 Jun 2017 16:16:32 GMT
ADD file:5aff8c59a70783352d1d5d5b24ddd27b77d9cdc5917992febe9d92901f78a8b3 in / 
# Fri, 02 Jun 2017 16:16:33 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 02 Jun 2017 16:16:35 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 02 Jun 2017 16:16:36 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 02 Jun 2017 16:16:38 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 02 Jun 2017 16:16:38 GMT
CMD ["/bin/bash"]
# Sat, 03 Jun 2017 01:56:37 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 421C365BD9FF1F717815A3895523BAEEB01FA116
# Sat, 03 Jun 2017 01:56:38 GMT
RUN echo "deb http://packages.ros.org/ros/ubuntu xenial main" > /etc/apt/sources.list.d/ros-latest.list
# Sat, 03 Jun 2017 01:57:10 GMT
RUN apt-get update && apt-get install --no-install-recommends -y     python-rosdep     python-rosinstall     python-vcstools     && rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 01:57:11 GMT
ENV LANG=C.UTF-8
# Sat, 03 Jun 2017 01:57:12 GMT
ENV LC_ALL=C.UTF-8
# Sat, 03 Jun 2017 01:57:23 GMT
RUN rosdep init     && rosdep update
# Sat, 03 Jun 2017 02:31:22 GMT
ENV ROS_DISTRO=lunar
# Sat, 03 Jun 2017 02:32:50 GMT
RUN apt-get update && apt-get install -y     ros-lunar-ros-core=1.3.1-0*     && rm -rf /var/lib/apt/lists/*
# Sat, 03 Jun 2017 02:32:53 GMT
COPY file:824303428ad16ae6296df253434e00a00126dc8404f740a8b885c9f61a2f5fcb in / 
# Sat, 03 Jun 2017 02:32:54 GMT
ENTRYPOINT ["/ros_entrypoint.sh"]
# Sat, 03 Jun 2017 02:32:55 GMT
CMD ["bash"]
```

-	Layers:
	-	`sha256:bd97b43c27e332fc4e00edf827bbc26369ad375187ce6eee91c616ad275884b1`  
		Last Modified: Fri, 19 May 2017 22:35:30 GMT  
		Size: 46.9 MB (46933232 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6960dc1aba1816652969986284410927a5d942bf8042e077a3ebc8d1c58bb432`  
		Last Modified: Fri, 02 Jun 2017 16:23:28 GMT  
		Size: 814.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b61829b0db5f4033ff48cbf3495271c8410c76e6396b56f15a79c3f7b5b7845`  
		Last Modified: Fri, 02 Jun 2017 16:23:27 GMT  
		Size: 512.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f88dc826b144c661a8d1d08561e1ff3711f527042955505e9f3e563bdb2281f`  
		Last Modified: Fri, 02 Jun 2017 16:23:28 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73b3859b1e43f3ff32f10055951a568a9ad5ab6dc4ab61818b117b6912088f3d`  
		Last Modified: Fri, 02 Jun 2017 16:23:28 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:27d60414a57ed486651a742bd6f1a8d57e06ffeb19866d004f32646fecd41e12`  
		Last Modified: Sat, 03 Jun 2017 03:29:00 GMT  
		Size: 13.1 KB (13079 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d93e52c3383b0c079b3babdc3ce7c0447f41dc21baa997f81a2631acba1af786`  
		Last Modified: Sat, 03 Jun 2017 03:29:01 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:357b9c9b16723f3af3f8ab490b0a56518b9474e5fea894e04414c369d4af0e0d`  
		Last Modified: Sat, 03 Jun 2017 03:29:28 GMT  
		Size: 58.8 MB (58779948 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c791091ba5c89739438557c06949b3cb21ada271a02e2c29c1b1b103098401`  
		Last Modified: Sat, 03 Jun 2017 03:29:01 GMT  
		Size: 715.4 KB (715368 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e606744e6b66f53316f570b15561f5c9688d08036d91dd03c99cd54734cb577`  
		Last Modified: Sat, 03 Jun 2017 03:35:56 GMT  
		Size: 193.0 MB (193044275 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8f8d44623741d74046454f2d0d1f1c849ec75bf8f613168c57bbc0695c75730`  
		Last Modified: Sat, 03 Jun 2017 03:35:00 GMT  
		Size: 194.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
