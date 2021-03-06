## `arangodb:latest`

```console
$ docker pull arangodb@sha256:f9a90b3d720b5c21a09e228756361db69d7141dca213fb7131c65be738db2758
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `arangodb:latest` - linux; amd64

```console
$ docker pull arangodb@sha256:c7a15ce4af3fb650eab56e542ca44eab8c9a64205fff81a1b16c6acb47ef2f6b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **112.2 MB (112214675 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:939e7c08c324989642f5fbdaed3e3bc9f236c4252c4b13bdee9dfc70c04d0401`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["arangod"]`

```dockerfile
# Tue, 12 Dec 2017 01:44:20 GMT
ADD file:eb2519421c9794ccc99d483c07f59ba305531bc9b4dc294e74d2ddb7de69e52a in / 
# Tue, 12 Dec 2017 01:44:21 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 03:13:36 GMT
MAINTAINER Frank Celler <info@arangodb.com>
# Tue, 12 Dec 2017 03:13:36 GMT
ENV ARCHITECTURE=amd64
# Tue, 12 Dec 2017 03:13:36 GMT
ENV DEB_PACKAGE_VERSION=1
# Mon, 08 Jan 2018 20:15:47 GMT
ENV ARANGO_VERSION=3.3.2
# Mon, 08 Jan 2018 20:15:47 GMT
ENV ARANGO_URL=https://download.arangodb.com/arangodb33/Debian_9.0
# Mon, 08 Jan 2018 20:15:47 GMT
ENV ARANGO_PACKAGE=arangodb3-3.3.2-1_amd64.deb
# Mon, 08 Jan 2018 20:15:48 GMT
ENV ARANGO_PACKAGE_URL=https://download.arangodb.com/arangodb33/Debian_9.0/amd64/arangodb3-3.3.2-1_amd64.deb
# Mon, 08 Jan 2018 20:15:48 GMT
ENV ARANGO_SIGNATURE_URL=https://download.arangodb.com/arangodb33/Debian_9.0/amd64/arangodb3-3.3.2-1_amd64.deb.asc
# Mon, 08 Jan 2018 20:15:55 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends gpg dirmngr     &&     rm -rf /var/lib/apt/lists/*
# Mon, 08 Jan 2018 20:15:59 GMT
RUN gpg --keyserver hkps://hkps.pool.sks-keyservers.net --recv-keys CD8CB0F1E0AD5B52E93F41E7EA93F5E56E751E9B
# Mon, 08 Jan 2018 20:16:08 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends         libjemalloc1         ca-certificates         pwgen         curl     &&     rm -rf /var/lib/apt/lists/*
# Mon, 08 Jan 2018 20:16:13 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 08 Jan 2018 20:16:28 GMT
RUN curl --fail -O ${ARANGO_SIGNATURE_URL} &&           curl --fail -O ${ARANGO_PACKAGE_URL} &&             gpg --verify ${ARANGO_PACKAGE}.asc &&     (echo arangodb3 arangodb3/password password test | debconf-set-selections) &&     (echo arangodb3 arangodb3/password_again password test | debconf-set-selections) &&     DEBIAN_FRONTEND="noninteractive" dpkg -i ${ARANGO_PACKAGE} &&     rm -rf /var/lib/arangodb3/* &&     sed -ri         -e 's!127\.0\.0\.1!0.0.0.0!g'         -e 's!^(file\s*=).*!\1 -!'         -e 's!^#\s*uid\s*=.*!uid = arangodb!'         -e 's!^#\s*gid\s*=.*!gid = arangodb!'         /etc/arangodb3/arangod.conf     &&     rm -f ${ARANGO_PACKAGE}*
# Mon, 08 Jan 2018 20:16:29 GMT
VOLUME [/var/lib/arangodb3 /var/lib/arangodb3-apps]
# Mon, 08 Jan 2018 20:16:29 GMT
COPY file:c8c98381ee5ef4e7c71a4913d8a58664a5d0b6674fb044613e151b1a6f4d73ac in /entrypoint.sh 
# Mon, 08 Jan 2018 20:16:30 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 08 Jan 2018 20:16:30 GMT
EXPOSE 8529/tcp
# Mon, 08 Jan 2018 20:16:31 GMT
CMD ["arangod"]
```

-	Layers:
	-	`sha256:723254a2c089166d4bcfa917be0181ddbecd94971ebfe85792d96e7e29be9c68`  
		Last Modified: Tue, 12 Dec 2017 01:53:22 GMT  
		Size: 45.1 MB (45121631 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68b0195e648071fb5136cbf6a48e7f5fd17a3f8ebc732d6773f679b688e2919b`  
		Last Modified: Mon, 08 Jan 2018 20:23:48 GMT  
		Size: 6.9 MB (6921023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1749c1245552d7b0472f3009ac7a927e1a3c14af921c4af330696437da211619`  
		Last Modified: Mon, 08 Jan 2018 20:23:44 GMT  
		Size: 3.5 KB (3469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b53d6f831aa7101dca221fd914e6d0e1068ba9694352d2468f695b6a95d5f530`  
		Last Modified: Mon, 08 Jan 2018 20:23:46 GMT  
		Size: 7.4 MB (7351463 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:844761c54c1bd5712cadb232110d162dc498ac3fd604b1a6369ad5a35ee910e8`  
		Last Modified: Mon, 08 Jan 2018 20:23:45 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fa449ffc8739fa2b12108bc5b8d6311ce29d290865c75afbe3ccbbeecc2978f`  
		Last Modified: Mon, 08 Jan 2018 20:23:57 GMT  
		Size: 52.8 MB (52815136 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b76f006d7276fb6d0854c4a997732de001e0419c71404e13e3ec899f6f9dbab5`  
		Last Modified: Mon, 08 Jan 2018 20:23:45 GMT  
		Size: 1.8 KB (1838 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
