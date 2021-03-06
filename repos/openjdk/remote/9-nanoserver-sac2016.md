## `openjdk:9-nanoserver-sac2016`

```console
$ docker pull openjdk@sha256:63448904ffad2ea165e6330cb95c8c6e795e15c31dac789b5fc5b0130f92d09b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64

### `openjdk:9-nanoserver-sac2016` - windows version 10.0.14393.2007; amd64

```console
$ docker pull openjdk@sha256:8d3803e348086f526262b84b031d56ad3edeb926193428c9fdd79fe69e8c6653
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **596.2 MB (596194987 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a88bc968baf1e2598c82258e74177df34f24069cd2e88dd34ad6f53e2bbaffd9`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:02 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:05:51 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 10:05:52 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Fri, 05 Jan 2018 10:06:59 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Fri, 05 Jan 2018 10:11:05 GMT
ENV JAVA_VERSION=9.0.1
# Fri, 05 Jan 2018 10:11:05 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.1-1
# Fri, 05 Jan 2018 10:11:06 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.1-1.b01.ojdkbuild.windows.x86_64.zip
# Fri, 05 Jan 2018 10:11:07 GMT
ENV JAVA_OJDKBUILD_SHA256=53d857727194635546d8af1e9c93ff272b737a46c1a03ef3d99b8078ab4e11f2
# Fri, 05 Jan 2018 10:12:42 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 10:12:45 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:764aee428c28f0935a6ded2a2730509373e1357648795b609b911dd46aa06257`  
		Last Modified: Thu, 04 Jan 2018 20:07:02 GMT  
		Size: 150.4 MB (150357748 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:954c60e18caf74c1c34ea38a04c2d8c7a2e4e2ae3658951596ace699a3894207`  
		Last Modified: Fri, 05 Jan 2018 10:14:14 GMT  
		Size: 922.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7b6582b2ddc6eb91d5ab41b0e8486aa2bf55f233601cf5aef9b649e5ac11e1a`  
		Last Modified: Fri, 05 Jan 2018 10:14:14 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da7337715dda7f285d15244ca3b41290be3077379f614896a8d7ac302635ef27`  
		Last Modified: Fri, 05 Jan 2018 10:14:14 GMT  
		Size: 845.8 KB (845757 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ced4bd322207533afd882cd449aff35687ae0306dddd95a383ef870e70596890`  
		Last Modified: Fri, 05 Jan 2018 10:15:37 GMT  
		Size: 950.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63fa4391717fc59b098e5ee4d4d82d7c0913252f37fccf07331230461fa8d1ca`  
		Last Modified: Fri, 05 Jan 2018 10:15:34 GMT  
		Size: 952.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e69c401aa35c588009c7661c3b9a7dc3002c4923f47d9c1e3333bcd121204692`  
		Last Modified: Fri, 05 Jan 2018 10:15:34 GMT  
		Size: 942.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a5c7109118d42c187f960da8d19e1d09ed248e2630b132a249d909475c01f18`  
		Last Modified: Fri, 05 Jan 2018 10:15:34 GMT  
		Size: 944.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a861d04e8f9c0e6c30378ff48a1f445d9f925de15cfa2eb42bc369a51fd69ee9`  
		Last Modified: Fri, 05 Jan 2018 10:15:53 GMT  
		Size: 192.3 MB (192293871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68a5ec89ab8bb0c8ab94955db6d0a9ed7617811d4bc85c08b814d27ecd988f47`  
		Last Modified: Fri, 05 Jan 2018 10:15:34 GMT  
		Size: 954.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
