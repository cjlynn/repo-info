<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `bonita`

-	[`bonita:7.5.4`](#bonita754)
-	[`bonita:7.6.1`](#bonita761)
-	[`bonita:latest`](#bonitalatest)

## `bonita:7.5.4`

```console
$ docker pull bonita@sha256:5e7519907d57c925add5f9d7e48a2ba94e7c1348d6a365e7464c4b3b52055ead
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `bonita:7.5.4` - linux; amd64

```console
$ docker pull bonita@sha256:1e81e131c680bb701417c859632426d18a0cc4d5ccab57c3383cbc125649910a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **213.9 MB (213865015 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:808e842465c728e96932b2b11763f3d2ffaadcf94c511b3094bf962d750f0c7b`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 14 Dec 2017 20:59:45 GMT
ADD file:f5a2d04c3f3cafada15eb32e4e8d971e48ef11724939c399a8664bf498111e67 in / 
# Thu, 14 Dec 2017 20:59:46 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 14 Dec 2017 20:59:46 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 20:59:47 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 14 Dec 2017 20:59:48 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 14 Dec 2017 20:59:48 GMT
CMD ["/bin/bash"]
# Thu, 14 Dec 2017 21:25:52 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 14 Dec 2017 21:26:21 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 21:26:22 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 14 Dec 2017 21:26:23 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 14 Dec 2017 21:26:25 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 14 Dec 2017 21:26:29 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 14 Dec 2017 21:26:29 GMT
ARG BONITA_VERSION
# Thu, 14 Dec 2017 21:26:30 GMT
ARG TOMCAT_VERSION
# Thu, 14 Dec 2017 21:26:30 GMT
ARG BONITA_SHA256
# Thu, 14 Dec 2017 21:26:30 GMT
ARG BONITA_URL
# Thu, 14 Dec 2017 21:26:30 GMT
ENV BONITA_VERSION=7.5.4
# Thu, 14 Dec 2017 21:26:30 GMT
ENV TOMCAT_VERSION=7.0.76
# Thu, 14 Dec 2017 21:26:31 GMT
ENV BONITA_SHA256=b7ccec231d9083b1b532b0aeaa4de3d38d91cae12df1725f8a802be5be170d21
# Thu, 14 Dec 2017 21:26:31 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaBPMCommunity-7.5.4-Tomcat-7.0.76.zip
# Thu, 14 Dec 2017 21:26:43 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 14 Dec 2017 21:26:44 GMT
RUN sha256sum /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 14 Dec 2017 21:26:45 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 14 Dec 2017 21:26:46 GMT
VOLUME [/opt/bonita]
# Thu, 14 Dec 2017 21:26:46 GMT
COPY dir:67158d50f6a23f242c6ece683aa22b62bf43e8403082c8a4b4c012ca3a3a0ac5 in /opt/files 
# Thu, 14 Dec 2017 21:26:46 GMT
COPY dir:9e855bbda97f640b6f8a3bf683a8ededee121c2f7673879b001ba4ea3a53d38b in /opt/templates 
# Thu, 14 Dec 2017 21:26:47 GMT
EXPOSE 8080/tcp
# Thu, 14 Dec 2017 21:26:47 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:50aff78429b146489e8a6cb9334d93a6d81d5de2edc4fbf5e2d4d9253625753e`  
		Last Modified: Sun, 03 Dec 2017 11:19:40 GMT  
		Size: 42.7 MB (42743207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6d82e297bce031a3de1fa8c1587535e34579abce09a61e37f5a225a8667422f`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:275abb2c8a6f1ce8e67a388a11f3cc014e98b36ff993a6ed1cc7cd6ecb4dd61b`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 621.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f15a39356d6fc1df0a77012bf1aa2150b683e46be39d1c51bc7a320f913e322`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc0342a94c89e477c821328ccb542e6fb86ce4ef4ebbf1098e85669e051ef0dd`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2878afe5a5a83db5d70bcdf51bf7c252a3a95ac0bc5a371fece43b75dd4cba4e`  
		Last Modified: Thu, 14 Dec 2017 21:27:47 GMT  
		Size: 82.7 MB (82653769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5bae80266d549ecfc8d63902cf706d35a5ff7bda42b0539f7dad0051150bde71`  
		Last Modified: Thu, 14 Dec 2017 21:27:30 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d781236de934d5bf03813ff6a272d30c22cf86dedd4fe82ec4ad44a1d44db37`  
		Last Modified: Thu, 14 Dec 2017 21:27:30 GMT  
		Size: 2.0 KB (2040 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a1d2d9af6f4012319ae58ef6f5b6e2d8bc6b5f14daee27ca16466d09276059c`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 133.2 KB (133184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61ac9ab67e6a30573c9b3e7fc5dd7568b6858821b91dc244375c1889da48c44b`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 818.6 KB (818558 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e66874daeb1925f32fe4bb55905edc462cfd867aba5365403ad213a746dc77f5`  
		Last Modified: Thu, 14 Dec 2017 21:27:33 GMT  
		Size: 87.5 MB (87503859 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bff7ee9fb7deed819c7128b71665836e9c45a77cc0c339906e0d847a0f0e60f`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 6.2 KB (6176 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e638a67b0f0cbe4daa0b6c32b91209e7c0edd5541ea7097dca812f2e14ff5d44`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 1.6 KB (1609 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `bonita:7.6.1`

```console
$ docker pull bonita@sha256:8e36706bc7270409626fc47c5005d414b84113eb328884b4879534a07986d784
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `bonita:7.6.1` - linux; amd64

```console
$ docker pull bonita@sha256:f0ce4f67552d62b3f6bf2b571abfb9a64d80f8eadda2bd5b372a6e199bb0b461
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **214.7 MB (214677280 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:02e8eb69f9780c69703a9644aaef36f6d0a8ba0df4fd3a59e0e413c8a3aa135c`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 14 Dec 2017 20:59:45 GMT
ADD file:f5a2d04c3f3cafada15eb32e4e8d971e48ef11724939c399a8664bf498111e67 in / 
# Thu, 14 Dec 2017 20:59:46 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 14 Dec 2017 20:59:46 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 20:59:47 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 14 Dec 2017 20:59:48 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 14 Dec 2017 20:59:48 GMT
CMD ["/bin/bash"]
# Thu, 14 Dec 2017 21:25:52 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 14 Dec 2017 21:26:21 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 21:26:22 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 14 Dec 2017 21:26:23 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 14 Dec 2017 21:26:25 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 14 Dec 2017 21:26:29 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 14 Dec 2017 21:26:29 GMT
ARG BONITA_VERSION
# Thu, 14 Dec 2017 21:26:30 GMT
ARG TOMCAT_VERSION
# Thu, 14 Dec 2017 21:26:30 GMT
ARG BONITA_SHA256
# Thu, 14 Dec 2017 21:26:30 GMT
ARG BONITA_URL
# Thu, 04 Jan 2018 18:54:51 GMT
ENV BONITA_VERSION=7.6.1
# Thu, 04 Jan 2018 18:54:52 GMT
ENV TOMCAT_VERSION=8.5.23
# Thu, 04 Jan 2018 18:54:52 GMT
ENV BONITA_SHA256=a35359dbaf4ea4bebeb520a22d733d93625281080f4cbad581b0ff7581b94785
# Thu, 04 Jan 2018 18:54:52 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.1-Tomcat-8.5.23.zip
# Thu, 04 Jan 2018 18:55:07 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 04 Jan 2018 18:55:08 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 04 Jan 2018 18:55:09 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 04 Jan 2018 18:55:09 GMT
VOLUME [/opt/bonita]
# Thu, 04 Jan 2018 18:55:10 GMT
COPY dir:922ea6ebf17819d868d6aee25bb5f7606ee9d4422a9d433bf71ce223d52a3f98 in /opt/files 
# Thu, 04 Jan 2018 18:55:10 GMT
COPY dir:8ca85ca324e0aeed811c4bd64a86bf6cebd3e105fb39fa3cf3c232fd56be7323 in /opt/templates 
# Thu, 04 Jan 2018 18:55:10 GMT
EXPOSE 8080/tcp
# Thu, 04 Jan 2018 18:55:11 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:50aff78429b146489e8a6cb9334d93a6d81d5de2edc4fbf5e2d4d9253625753e`  
		Last Modified: Sun, 03 Dec 2017 11:19:40 GMT  
		Size: 42.7 MB (42743207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6d82e297bce031a3de1fa8c1587535e34579abce09a61e37f5a225a8667422f`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:275abb2c8a6f1ce8e67a388a11f3cc014e98b36ff993a6ed1cc7cd6ecb4dd61b`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 621.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f15a39356d6fc1df0a77012bf1aa2150b683e46be39d1c51bc7a320f913e322`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc0342a94c89e477c821328ccb542e6fb86ce4ef4ebbf1098e85669e051ef0dd`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2878afe5a5a83db5d70bcdf51bf7c252a3a95ac0bc5a371fece43b75dd4cba4e`  
		Last Modified: Thu, 14 Dec 2017 21:27:47 GMT  
		Size: 82.7 MB (82653769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5bae80266d549ecfc8d63902cf706d35a5ff7bda42b0539f7dad0051150bde71`  
		Last Modified: Thu, 14 Dec 2017 21:27:30 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d781236de934d5bf03813ff6a272d30c22cf86dedd4fe82ec4ad44a1d44db37`  
		Last Modified: Thu, 14 Dec 2017 21:27:30 GMT  
		Size: 2.0 KB (2040 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a1d2d9af6f4012319ae58ef6f5b6e2d8bc6b5f14daee27ca16466d09276059c`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 133.2 KB (133184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61ac9ab67e6a30573c9b3e7fc5dd7568b6858821b91dc244375c1889da48c44b`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 818.6 KB (818558 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0434f2e937d6cb4f13ce6a6b149c7bb2559bb667a99eee85c860a9056f38bb98`  
		Last Modified: Thu, 04 Jan 2018 18:55:34 GMT  
		Size: 88.3 MB (88315873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9d430c41c619c2ce98fcf60b6a92ce0473de7bcf65f7243baf49aeedbe9989f`  
		Last Modified: Thu, 04 Jan 2018 18:55:27 GMT  
		Size: 6.4 KB (6382 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a8ccbcf2d8fb6039c2d80bfffb303e077ba0276119db03d7f3183fbfee71c7f`  
		Last Modified: Thu, 04 Jan 2018 18:55:28 GMT  
		Size: 1.7 KB (1654 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `bonita:latest`

```console
$ docker pull bonita@sha256:8e36706bc7270409626fc47c5005d414b84113eb328884b4879534a07986d784
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `bonita:latest` - linux; amd64

```console
$ docker pull bonita@sha256:f0ce4f67552d62b3f6bf2b571abfb9a64d80f8eadda2bd5b372a6e199bb0b461
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **214.7 MB (214677280 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:02e8eb69f9780c69703a9644aaef36f6d0a8ba0df4fd3a59e0e413c8a3aa135c`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Thu, 14 Dec 2017 20:59:45 GMT
ADD file:f5a2d04c3f3cafada15eb32e4e8d971e48ef11724939c399a8664bf498111e67 in / 
# Thu, 14 Dec 2017 20:59:46 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 14 Dec 2017 20:59:46 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 20:59:47 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 14 Dec 2017 20:59:48 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 14 Dec 2017 20:59:48 GMT
CMD ["/bin/bash"]
# Thu, 14 Dec 2017 21:25:52 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Thu, 14 Dec 2017 21:26:21 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.7   openjdk-8-jre-headless   postgresql-client   unzip   curl   zip   && rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 21:26:22 GMT
RUN mkdir /opt/custom-init.d/
# Thu, 14 Dec 2017 21:26:23 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Thu, 14 Dec 2017 21:26:25 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Thu, 14 Dec 2017 21:26:29 GMT
RUN curl -fsSL "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture)" -o /usr/local/bin/gosu   && curl -fsSL "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture).asc" -o /usr/local/bin/gosu.asc   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Thu, 14 Dec 2017 21:26:29 GMT
ARG BONITA_VERSION
# Thu, 14 Dec 2017 21:26:30 GMT
ARG TOMCAT_VERSION
# Thu, 14 Dec 2017 21:26:30 GMT
ARG BONITA_SHA256
# Thu, 14 Dec 2017 21:26:30 GMT
ARG BONITA_URL
# Thu, 04 Jan 2018 18:54:51 GMT
ENV BONITA_VERSION=7.6.1
# Thu, 04 Jan 2018 18:54:52 GMT
ENV TOMCAT_VERSION=8.5.23
# Thu, 04 Jan 2018 18:54:52 GMT
ENV BONITA_SHA256=a35359dbaf4ea4bebeb520a22d733d93625281080f4cbad581b0ff7581b94785
# Thu, 04 Jan 2018 18:54:52 GMT
ENV BONITA_URL=https://download.forge.ow2.org/bonita/BonitaCommunity-7.6.1-Tomcat-8.5.23.zip
# Thu, 04 Jan 2018 18:55:07 GMT
RUN mkdir /opt/files   && curl -fsSL ${BONITA_URL} -o /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 04 Jan 2018 18:55:08 GMT
RUN sha256sum /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Thu, 04 Jan 2018 18:55:09 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Thu, 04 Jan 2018 18:55:09 GMT
VOLUME [/opt/bonita]
# Thu, 04 Jan 2018 18:55:10 GMT
COPY dir:922ea6ebf17819d868d6aee25bb5f7606ee9d4422a9d433bf71ce223d52a3f98 in /opt/files 
# Thu, 04 Jan 2018 18:55:10 GMT
COPY dir:8ca85ca324e0aeed811c4bd64a86bf6cebd3e105fb39fa3cf3c232fd56be7323 in /opt/templates 
# Thu, 04 Jan 2018 18:55:10 GMT
EXPOSE 8080/tcp
# Thu, 04 Jan 2018 18:55:11 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:50aff78429b146489e8a6cb9334d93a6d81d5de2edc4fbf5e2d4d9253625753e`  
		Last Modified: Sun, 03 Dec 2017 11:19:40 GMT  
		Size: 42.7 MB (42743207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6d82e297bce031a3de1fa8c1587535e34579abce09a61e37f5a225a8667422f`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:275abb2c8a6f1ce8e67a388a11f3cc014e98b36ff993a6ed1cc7cd6ecb4dd61b`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 621.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f15a39356d6fc1df0a77012bf1aa2150b683e46be39d1c51bc7a320f913e322`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc0342a94c89e477c821328ccb542e6fb86ce4ef4ebbf1098e85669e051ef0dd`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2878afe5a5a83db5d70bcdf51bf7c252a3a95ac0bc5a371fece43b75dd4cba4e`  
		Last Modified: Thu, 14 Dec 2017 21:27:47 GMT  
		Size: 82.7 MB (82653769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5bae80266d549ecfc8d63902cf706d35a5ff7bda42b0539f7dad0051150bde71`  
		Last Modified: Thu, 14 Dec 2017 21:27:30 GMT  
		Size: 122.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d781236de934d5bf03813ff6a272d30c22cf86dedd4fe82ec4ad44a1d44db37`  
		Last Modified: Thu, 14 Dec 2017 21:27:30 GMT  
		Size: 2.0 KB (2040 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a1d2d9af6f4012319ae58ef6f5b6e2d8bc6b5f14daee27ca16466d09276059c`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 133.2 KB (133184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61ac9ab67e6a30573c9b3e7fc5dd7568b6858821b91dc244375c1889da48c44b`  
		Last Modified: Thu, 14 Dec 2017 21:27:28 GMT  
		Size: 818.6 KB (818558 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0434f2e937d6cb4f13ce6a6b149c7bb2559bb667a99eee85c860a9056f38bb98`  
		Last Modified: Thu, 04 Jan 2018 18:55:34 GMT  
		Size: 88.3 MB (88315873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9d430c41c619c2ce98fcf60b6a92ce0473de7bcf65f7243baf49aeedbe9989f`  
		Last Modified: Thu, 04 Jan 2018 18:55:27 GMT  
		Size: 6.4 KB (6382 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a8ccbcf2d8fb6039c2d80bfffb303e077ba0276119db03d7f3183fbfee71c7f`  
		Last Modified: Thu, 04 Jan 2018 18:55:28 GMT  
		Size: 1.7 KB (1654 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
