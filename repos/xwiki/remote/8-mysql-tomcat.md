## `xwiki:8-mysql-tomcat`

```console
$ docker pull xwiki@sha256:aef4283941e8b977a345ee20f8d475905c26c9793a33fa908a81d540a93d810a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `xwiki:8-mysql-tomcat` - linux; amd64

```console
$ docker pull xwiki@sha256:e6c8ea3977bcc30ef488d536a69829d3d5985e2561f5fb20062771148b664be9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **633.6 MB (633597966 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0073b1cccc18b4859ad49aca3fd9dbbcb9570a2360373743c9ca4fdcab842d68`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["xwiki"]`

```dockerfile
# Tue, 12 Dec 2017 01:44:20 GMT
ADD file:eb2519421c9794ccc99d483c07f59ba305531bc9b4dc294e74d2ddb7de69e52a in / 
# Tue, 12 Dec 2017 01:44:21 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 07:54:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 07:54:15 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 15:16:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 15:16:23 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 15:16:24 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 15:16:25 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 15:16:25 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Dec 2017 15:16:26 GMT
ENV JAVA_VERSION=8u151
# Tue, 12 Dec 2017 15:16:26 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Tue, 12 Dec 2017 15:16:26 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 12 Dec 2017 15:17:32 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Dec 2017 15:17:36 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 12 Dec 2017 18:35:51 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Tue, 12 Dec 2017 18:35:51 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Dec 2017 18:35:52 GMT
RUN mkdir -p "$CATALINA_HOME"
# Tue, 12 Dec 2017 18:35:58 GMT
WORKDIR /usr/local/tomcat
# Tue, 12 Dec 2017 18:35:58 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Tue, 12 Dec 2017 18:35:59 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Tue, 12 Dec 2017 18:35:59 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Thu, 11 Jan 2018 00:27:59 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Thu, 11 Jan 2018 00:28:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Thu, 11 Jan 2018 00:28:09 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 713DA88BE50911535FE716F5208B0AB1D63011C7 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 11 Jan 2018 00:28:20 GMT
RUN set -ex; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Thu, 11 Jan 2018 00:43:10 GMT
ENV TOMCAT_MAJOR=8
# Thu, 11 Jan 2018 00:48:03 GMT
ENV TOMCAT_VERSION=8.5.24
# Thu, 11 Jan 2018 00:48:04 GMT
ENV TOMCAT_SHA1=9e26ba61c5665aafc849073edeb769be555283cd
# Thu, 11 Jan 2018 00:48:04 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz
# Thu, 11 Jan 2018 00:48:04 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz.asc
# Thu, 11 Jan 2018 00:48:28 GMT
RUN set -eux; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	nativeBuildDeps=" 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION 	"; 	apt-get update; 	apt-get install -y --no-install-recommends $nativeBuildDeps; 	rm -rf /var/lib/apt/lists/*; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	apt-get purge -y --auto-remove $nativeBuildDeps; 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 11 Jan 2018 00:48:30 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 11 Jan 2018 00:48:30 GMT
EXPOSE 8080/tcp
# Thu, 11 Jan 2018 00:48:30 GMT
CMD ["catalina.sh" "run"]
# Thu, 11 Jan 2018 02:00:42 GMT
MAINTAINER Vincent Massol <vincent@massol.net>
# Thu, 11 Jan 2018 02:01:39 GMT
RUN apt-get update &&   apt-get --no-install-recommends -y install     curl     libreoffice     unzip     procps     libmysql-java &&   rm -rf /var/lib/apt/lists/*
# Thu, 11 Jan 2018 02:01:40 GMT
ENV XWIKI_VERSION=8.4.5
# Thu, 11 Jan 2018 02:01:40 GMT
ENV XWIKI_URL_PREFIX=http://maven.xwiki.org/releases/org/xwiki/enterprise/xwiki-enterprise-web/8.4.5
# Thu, 11 Jan 2018 02:01:40 GMT
ENV XWIKI_DOWNLOAD_SHA256=52ed122c44984748a729a784c94cb70ccf0d2fa34c2340d0fd45c75deb3b0bc9
# Thu, 11 Jan 2018 02:02:17 GMT
RUN rm -rf /usr/local/tomcat/webapps/* &&   mkdir -p /usr/local/tomcat/temp &&   mkdir -p /usr/local/xwiki/data &&   curl -fSL "${XWIKI_URL_PREFIX}/xwiki-enterprise-web-${XWIKI_VERSION}.war" -o xwiki.war &&   echo "$XWIKI_DOWNLOAD_SHA256 xwiki.war" | sha256sum -c - &&   unzip -d /usr/local/tomcat/webapps/ROOT xwiki.war &&   rm -f xwiki.war
# Thu, 11 Jan 2018 02:11:33 GMT
RUN cp /usr/share/java/mysql-connector-java-*.jar /usr/local/tomcat/webapps/ROOT/WEB-INF/lib/
# Thu, 11 Jan 2018 02:11:33 GMT
COPY file:a5eb2bffb2fd9cdddac5e77040b6f670c8dd62aa8af8ea010e4a65f2291ae6ab in /usr/local/tomcat/bin/ 
# Thu, 11 Jan 2018 02:11:34 GMT
COPY file:1c0736cd925afea380b7be25664cbe8411b510ba081ed0ffd36fc65197d467f4 in /usr/local/tomcat/webapps/ROOT/WEB-INF/hibernate.cfg.xml 
# Thu, 11 Jan 2018 02:11:34 GMT
RUN sed -i 's/<id>org.xwiki.enterprise:xwiki-enterprise-web/<id>org.xwiki.enterprise:xwiki-enterprise-docker/'   /usr/local/tomcat/webapps/ROOT/META-INF/extension.xed
# Thu, 11 Jan 2018 02:11:35 GMT
COPY file:b6c5245e38f1c0b353526e42f4efb43cc80fb1685948a9da5da26b9e55659eb9 in /usr/local/bin/docker-entrypoint.sh 
# Thu, 11 Jan 2018 02:11:35 GMT
VOLUME [/usr/local/xwiki]
# Thu, 11 Jan 2018 02:11:35 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 11 Jan 2018 02:11:36 GMT
CMD ["xwiki"]
```

-	Layers:
	-	`sha256:723254a2c089166d4bcfa917be0181ddbecd94971ebfe85792d96e7e29be9c68`  
		Last Modified: Tue, 12 Dec 2017 01:53:22 GMT  
		Size: 45.1 MB (45121631 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abe15a44e12f84b4aac20d4f2b450ec8638cc0b176c9130d1802cb4fed17d953`  
		Last Modified: Tue, 12 Dec 2017 08:03:48 GMT  
		Size: 11.1 MB (11107352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:409a28e3cc3de08700c9d37c809a6d3aa43dc076402943919f4a78c286c60a0b`  
		Last Modified: Tue, 12 Dec 2017 08:03:48 GMT  
		Size: 4.3 MB (4335420 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9511c68044accc89061e19e40356126f629c1e3ace2ef524b0e3f02e64e6b10`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 852.3 KB (852274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d1b16e30bc84a10c110be2c4f0a35dce542c7d55869cf2f99b7753763aabdb1`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fc5a09c924277c26642af87cc8a057633582a6fb462141245d46a638d0f8cf5`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d34976006493631a54114beee079e51dd165df33f8f5ebfc04b0eeb12613bedb`  
		Last Modified: Tue, 12 Dec 2017 16:20:31 GMT  
		Size: 165.4 MB (165393574 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b70003f0c1097e6b4f30f66e223ce759edec1331f5c1a4569e24ce8f4d41632`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 272.2 KB (272151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc7887582e2e99620eb88831728398dd1877f5a16deaf40db4d6f7f5bfb8b5a0`  
		Last Modified: Tue, 12 Dec 2017 18:43:08 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2ab4f16586596fc8f2512509f62ac407c8be9d2688a4bc8b80395b0ed811635`  
		Last Modified: Thu, 11 Jan 2018 01:02:44 GMT  
		Size: 545.4 KB (545375 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6c51c315c970aff545b122198c4dbcbc0ab875709b69992b681ffacba8e8cf9`  
		Last Modified: Thu, 11 Jan 2018 01:02:41 GMT  
		Size: 110.4 KB (110411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37408e07e7d99a3ef140bc94d6da6f9beb5542373f27fc44e38192570e12e07a`  
		Last Modified: Thu, 11 Jan 2018 01:27:28 GMT  
		Size: 10.5 MB (10479289 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4968437fe7af7efdedf3b6944fd59a0856dc90c9776441115cb8fd819167bbf2`  
		Last Modified: Thu, 11 Jan 2018 01:27:26 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08c4114f4edca65b3de846276e1fcf78ac27c86aac1bb78cb73fcd84ab2b86ab`  
		Last Modified: Thu, 11 Jan 2018 02:20:52 GMT  
		Size: 157.4 MB (157383315 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c51fb9d4bcaa5c14898c2c90a1e694c546406fdca762b79477144cbffcc3062`  
		Last Modified: Thu, 11 Jan 2018 02:20:36 GMT  
		Size: 237.0 MB (237036100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e53ba59cadec1565474cd2ef3e16d890cc0f258c3301397f4cb4e5debbcb5469`  
		Last Modified: Thu, 11 Jan 2018 02:20:08 GMT  
		Size: 952.1 KB (952119 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d40a2d9ec9f38cced2655ff2358a226935ac3b6c4c91c48d8be7d648de5d1af`  
		Last Modified: Thu, 11 Jan 2018 02:20:08 GMT  
		Size: 263.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf01bbc71625d16b1d1ee1685442da4d94f8879195faf18f45e102484888efa7`  
		Last Modified: Thu, 11 Jan 2018 02:20:07 GMT  
		Size: 2.3 KB (2292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f5e37af740c2eecf28cb57440ad69bff4b37974ee820d6a83904e9a5c64498b`  
		Last Modified: Thu, 11 Jan 2018 02:20:07 GMT  
		Size: 3.7 KB (3721 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15ea4440e0bceea18171aa5c633b3cc2fa558e92ba55cdfa1e976ef3cc34bc97`  
		Last Modified: Thu, 11 Jan 2018 02:20:07 GMT  
		Size: 2.0 KB (2022 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
