## `golang:rc-nanoserver-sac2016`

```console
$ docker pull golang@sha256:13c5358d843d2dfdb34cee422ab90025ac00cc391ff77bce262365828330ff88
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64

### `golang:rc-nanoserver-sac2016` - windows version 10.0.14393.2007; amd64

```console
$ docker pull golang@sha256:9dc9e5743fe222834a58f0d36cc100f2c73cb036cc896b81b99cd39d885448b1
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **604.6 MB (604581747 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:334fafacaa81b4ad3441dfaef5bfcd546ecdd27038e938f4dabf71f379381628`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:02 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:05:51 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Mon, 08 Jan 2018 18:26:16 GMT
ENV GOPATH=C:\gopath
# Mon, 08 Jan 2018 18:27:21 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Mon, 08 Jan 2018 18:27:22 GMT
ENV GOLANG_VERSION=1.10beta1
# Mon, 08 Jan 2018 18:34:55 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'ff2789b7baf33f87111d30bac81ac1ae19dcc16bdd75553f9b5aceda14733a40'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Mon, 08 Jan 2018 18:34:57 GMT
WORKDIR C:\gopath
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
	-	`sha256:a86e7fa28644d6145ab3a303bf625643f98fd573f0c038ccd2aed1d1a7de6a9a`  
		Last Modified: Mon, 08 Jan 2018 19:55:41 GMT  
		Size: 942.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c3e186accae51f0eeb18ba54d31934fbb1db4dc4adcae8b4bbc186ce83d476f`  
		Last Modified: Mon, 08 Jan 2018 19:55:43 GMT  
		Size: 856.7 KB (856654 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43545c317c65dcf8ade47423d9ddd77ee50e2c430520df485c9fc9b0ebc674d6`  
		Last Modified: Mon, 08 Jan 2018 19:55:41 GMT  
		Size: 943.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6a21ff99adc7ce3d033250e292b830e16062b9f050d22d8b0fb7c45cc590df7`  
		Last Modified: Mon, 08 Jan 2018 19:59:00 GMT  
		Size: 200.7 MB (200672385 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:937910b99c86011e7ba97563263bc0929b0fb9f805b9ad39bfa3c9ced78936c7`  
		Last Modified: Mon, 08 Jan 2018 19:55:41 GMT  
		Size: 1.2 KB (1151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
