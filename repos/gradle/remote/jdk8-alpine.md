## `gradle:jdk8-alpine`

```console
$ docker pull gradle@sha256:24e2189b2a20f7a770841f4d2c8422f30385afa820ebfb3b36b710691d3db3ce
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `gradle:jdk8-alpine` - linux; amd64

```console
$ docker pull gradle@sha256:03cc494b1a734af96dccdbc54b2621cb058afc1289c8b3bbf41862807d521ca5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **148.1 MB (148089977 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:221680b4de3501e9a5b34986b7d196caaffe4acfed308916d127d405cbb96ec5`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 04:48:24 GMT
ENV LANG=C.UTF-8
# Wed, 10 Jan 2018 04:48:25 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 10 Jan 2018 04:50:19 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 10 Jan 2018 04:50:19 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 10 Jan 2018 04:50:19 GMT
ENV JAVA_VERSION=8u151
# Wed, 10 Jan 2018 04:50:19 GMT
ENV JAVA_ALPINE_VERSION=8.151.12-r0
# Wed, 10 Jan 2018 04:51:20 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 10 Jan 2018 08:29:07 GMT
CMD ["gradle"]
# Wed, 10 Jan 2018 08:29:08 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 10 Jan 2018 08:29:08 GMT
ENV GRADLE_VERSION=4.4.1
# Wed, 10 Jan 2018 08:29:08 GMT
ARG GRADLE_DOWNLOAD_SHA256=e7cf7d1853dfc30c1c44f571d3919eeeedef002823b66b6a988d27e919686389
# Wed, 10 Jan 2018 08:29:16 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e7cf7d1853dfc30c1c44f571d3919eeeedef002823b66b6a988d27e919686389
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		openssl 		unzip 		&& echo "Downloading Gradle" 	&& wget -O gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum -c - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mkdir /opt 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln -s "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& apk del .build-deps 		&& echo "Adding gradle user and group" 	&& addgroup -S -g 1000 gradle 	&& adduser -D -S -G gradle -u 1000 -s /bin/ash gradle 	&& mkdir /home/gradle/.gradle 	&& chown -R gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 10 Jan 2018 08:29:16 GMT
USER [gradle]
# Wed, 10 Jan 2018 08:29:16 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 10 Jan 2018 08:29:16 GMT
WORKDIR /home/gradle
# Wed, 10 Jan 2018 08:29:21 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e7cf7d1853dfc30c1c44f571d3919eeeedef002823b66b6a988d27e919686389
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:fd869c8b9b592f2fcb5ed4d6055d651ae18d5c2cce22f56896f0ff96cdcbcbf7`  
		Last Modified: Wed, 10 Jan 2018 04:56:54 GMT  
		Size: 70.2 MB (70227764 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9090e9c6653aeb879b30392f318a04d3d8337c42a22611305055515621fd90c8`  
		Last Modified: Wed, 10 Jan 2018 08:33:17 GMT  
		Size: 75.8 MB (75796299 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0caac28d5fb196a65ea1495cc663ec56f8c73d79fe576066b4c4eba0cbc3856d`  
		Last Modified: Wed, 10 Jan 2018 08:33:12 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
