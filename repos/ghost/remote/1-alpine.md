## `ghost:1-alpine`

```console
$ docker pull ghost@sha256:f3ce4b2be1d148bcd6ef8ee6c0b4fe7f44786c2a032dbc3f140372bcb4503903
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `ghost:1-alpine` - linux; amd64

```console
$ docker pull ghost@sha256:525c5c8d339bcca2def96d7b8acabe8ef3d265eb36da58164e651d3ff7fc785f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **141.2 MB (141212394 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:61a0ef7f152bdc1ceb53f7cbf3f7e0cd0a05e7eb4f72601f460e758034000b56`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["node","current\/index.js"]`

```dockerfile
# Tue, 09 Jan 2018 21:12:40 GMT
ADD file:69848cb51056edaf120230b6f218a79968ac797295c2cef6728332e1801357be in / 
# Tue, 09 Jan 2018 21:12:40 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 00:43:08 GMT
ENV NODE_VERSION=6.12.3
# Wed, 10 Jan 2018 00:56:02 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     B9AE9905FFD7803F25714661B63B535A4C206CA9     56730D5401028683275BD23C23EFEFE93C4CFFFE     77984A986EBC2AA786BC0F66B01FBB92821C587A   ; do     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ||     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ;   done     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -SLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Wed, 10 Jan 2018 00:56:45 GMT
ENV YARN_VERSION=1.3.2
# Wed, 10 Jan 2018 00:56:53 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg tar   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ||     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ;   done   && curl -fSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt/yarn   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/yarn --strip-components=1   && ln -s /opt/yarn/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn/bin/yarn /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && apk del .build-deps-yarn
# Wed, 10 Jan 2018 00:56:53 GMT
CMD ["node"]
# Wed, 10 Jan 2018 05:45:38 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Wed, 10 Jan 2018 05:45:50 GMT
RUN apk add --no-cache 		bash
# Wed, 10 Jan 2018 05:45:50 GMT
ENV NODE_ENV=production
# Wed, 10 Jan 2018 05:45:50 GMT
ENV GHOST_CLI_VERSION=1.4.2
# Wed, 10 Jan 2018 05:46:16 GMT
RUN npm install -g "ghost-cli@$GHOST_CLI_VERSION"
# Wed, 10 Jan 2018 05:46:17 GMT
ENV GHOST_INSTALL=/var/lib/ghost
# Wed, 10 Jan 2018 05:46:17 GMT
ENV GHOST_CONTENT=/var/lib/ghost/content
# Thu, 11 Jan 2018 01:32:42 GMT
ENV GHOST_VERSION=1.20.0
# Thu, 11 Jan 2018 01:33:35 GMT
RUN set -ex; 	mkdir -p "$GHOST_INSTALL"; 	chown node:node "$GHOST_INSTALL"; 		su-exec node ghost install "$GHOST_VERSION" --db sqlite3 --no-prompt --no-stack --no-setup --dir "$GHOST_INSTALL"; 		cd "$GHOST_INSTALL"; 	su-exec node ghost config --ip 0.0.0.0 --port 2368 --no-prompt --db sqlite3 --url http://localhost:2368 --dbpath "$GHOST_CONTENT/data/ghost.db"; 	su-exec node ghost config paths.contentPath "$GHOST_CONTENT"; 		su-exec node ln -s config.production.json "$GHOST_INSTALL/config.development.json"; 	readlink -f "$GHOST_INSTALL/config.development.json"; 		mv "$GHOST_CONTENT" "$GHOST_INSTALL/content.orig"; 	mkdir -p "$GHOST_CONTENT"; 	chown node:node "$GHOST_CONTENT"; 		"$GHOST_INSTALL/current/node_modules/knex-migrator/bin/knex-migrator" --version
# Thu, 11 Jan 2018 01:34:04 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/var/lib/ghost/current/node_modules/knex-migrator/bin
# Thu, 11 Jan 2018 01:34:04 GMT
WORKDIR /var/lib/ghost
# Thu, 11 Jan 2018 01:34:04 GMT
VOLUME [/var/lib/ghost/content]
# Thu, 11 Jan 2018 01:34:04 GMT
COPY file:fe4f8ce065580d78daf2ea3ae3ab9174f3edd7740df8b95889926dc1cdfe77b0 in /usr/local/bin 
# Thu, 11 Jan 2018 01:34:05 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 11 Jan 2018 01:34:05 GMT
EXPOSE 2368/tcp
# Thu, 11 Jan 2018 01:34:05 GMT
CMD ["node" "current/index.js"]
```

-	Layers:
	-	`sha256:81033e7c1d6a5b44a94bb6b40033a6e589f50fd6b61578da6fc809e61f83898d`  
		Last Modified: Tue, 09 Jan 2018 21:15:04 GMT  
		Size: 2.4 MB (2387570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4227978c61db5bbb8798c0171f0855f518ea835b42bc5ca5d5c083bd825c0766`  
		Last Modified: Wed, 10 Jan 2018 01:19:27 GMT  
		Size: 15.5 MB (15457822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d96df174e5f411c706757fdfc5fb561e71091e02898590e4cb15ea04d5991c7b`  
		Last Modified: Wed, 10 Jan 2018 01:19:21 GMT  
		Size: 1.0 MB (1017576 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b951a6cdab012c9c907b7ec51e95f20166f4492a4bb900e8b89f8f913865cae8`  
		Last Modified: Wed, 10 Jan 2018 05:48:58 GMT  
		Size: 8.4 KB (8361 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b168cf2b3652759447bf7dbcea613d5bfd607933e7144b0711dc2201b9d4bef`  
		Last Modified: Wed, 10 Jan 2018 05:49:03 GMT  
		Size: 1.1 MB (1112395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7887bc8dff8608c37658f88d28b64726f76fae1ea9a2375c3f7cc76c5bcdb3d8`  
		Last Modified: Wed, 10 Jan 2018 05:49:18 GMT  
		Size: 19.1 MB (19127280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0bac31403eeeaea5410d2d21f5a2e8a21b34028aeec426113a22e83fca838ac`  
		Last Modified: Thu, 11 Jan 2018 01:44:42 GMT  
		Size: 102.1 MB (102100829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d93a73f6bff20f7d331708ec7ed7585936d41cc9d415d78c76ac7a2cac25c106`  
		Last Modified: Thu, 11 Jan 2018 01:43:59 GMT  
		Size: 561.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
