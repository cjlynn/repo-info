## `neo4j:enterprise`

```console
$ docker pull neo4j@sha256:2d8247f0aeae8b94986a12d207ccdab7d58dd524d60d5e0d636284cccc9a2841
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `neo4j:enterprise` - linux; amd64

```console
$ docker pull neo4j@sha256:7ce0fc21b1e13993dc3be2d15ed9fe7efe81a5f46c6d393a5e113fdfd80a9ae0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **162.6 MB (162638326 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2059f24ddc25fd17f74cabc50cc8d17c498cebb6df5ff413100c33dcd34bdd49`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["neo4j"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 04:48:24 GMT
ENV LANG=C.UTF-8
# Wed, 10 Jan 2018 04:48:25 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 10 Jan 2018 04:51:56 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk/jre
# Wed, 10 Jan 2018 04:51:57 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 10 Jan 2018 04:51:57 GMT
ENV JAVA_VERSION=8u151
# Wed, 10 Jan 2018 04:51:57 GMT
ENV JAVA_ALPINE_VERSION=8.151.12-r0
# Wed, 10 Jan 2018 04:52:04 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 10 Jan 2018 08:41:39 GMT
RUN apk add --no-cache --quiet     bash     curl
# Wed, 10 Jan 2018 08:42:53 GMT
ENV NEO4J_SHA256=6330fd7b8fafb99584cadee77ecd5d607a44bce4978b4a90bfe96b4a500a193d NEO4J_TARBALL=neo4j-enterprise-3.3.1-unix.tar.gz NEO4J_EDITION=enterprise
# Wed, 10 Jan 2018 08:42:53 GMT
ARG NEO4J_URI=http://dist.neo4j.org/neo4j-enterprise-3.3.1-unix.tar.gz
# Wed, 10 Jan 2018 08:42:54 GMT
COPY file:2e411d607fa15f91ae6f4b515dde6bf3e158d34c0036556e00553ed1c50cd63d in /tmp/ 
# Wed, 10 Jan 2018 08:43:14 GMT
# ARGS: NEO4J_URI=http://dist.neo4j.org/neo4j-enterprise-3.3.1-unix.tar.gz
RUN curl --fail --silent --show-error --location --remote-name ${NEO4J_URI}     && echo "${NEO4J_SHA256}  ${NEO4J_TARBALL}" | sha256sum -csw -     && tar --extract --file ${NEO4J_TARBALL} --directory /var/lib     && mv /var/lib/neo4j-* /var/lib/neo4j     && rm ${NEO4J_TARBALL}     && mv /var/lib/neo4j/data /data     && ln -s /data /var/lib/neo4j/data     && apk del curl
# Wed, 10 Jan 2018 08:43:21 GMT
ENV PATH=/var/lib/neo4j/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 10 Jan 2018 08:43:22 GMT
WORKDIR /var/lib/neo4j
# Wed, 10 Jan 2018 08:43:22 GMT
VOLUME [/data]
# Wed, 10 Jan 2018 08:43:23 GMT
COPY file:b1f08b121281604fe08edf206463959271aee1f21c800af2c0f2a52d70db0f3e in /docker-entrypoint.sh 
# Wed, 10 Jan 2018 08:43:23 GMT
EXPOSE 7473/tcp 7474/tcp 7687/tcp
# Wed, 10 Jan 2018 08:43:23 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 10 Jan 2018 08:43:24 GMT
CMD ["neo4j"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5de5f69f42d765af6ffb6753242b18dd4a33602ad7d76df52064833e5c527cb4`  
		Last Modified: Wed, 10 Jan 2018 04:53:02 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa7536dd895ade2421a9a0fcf6e16485323f9e2e45e917b1ff18b0f648974626`  
		Last Modified: Wed, 10 Jan 2018 04:59:33 GMT  
		Size: 54.5 MB (54453948 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d58d533cf95026ab735f3e7683b1c3ed8fcb49358044c179adf20595beb7ba71`  
		Last Modified: Wed, 10 Jan 2018 09:29:33 GMT  
		Size: 1.7 MB (1689224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94283974be81a7c8cea89fd2dab4bc207645d6c97043a24eab0d260dc02a8c6a`  
		Last Modified: Wed, 10 Jan 2018 09:30:24 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1c5375dd4a779cf216288a019f9f8e102dd684b2591f313b6f8978ae30b279b`  
		Last Modified: Wed, 10 Jan 2018 09:30:38 GMT  
		Size: 104.4 MB (104426972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3a608921d48edada2bf57f4be26fff01c2388637060efcc11856b99bdf5958e3`  
		Last Modified: Wed, 10 Jan 2018 09:30:24 GMT  
		Size: 2.3 KB (2276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
