## `golang:rc-windowsservercore`

```console
$ docker pull golang@sha256:30515b8fe88ad9930e6f1989f78a78ce8d5ba0cc401f55e4d80856444e346ba1
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64
	-	windows version 10.0.16299.192; amd64

### `golang:rc-windowsservercore` - windows version 10.0.14393.2007; amd64

```console
$ docker pull golang@sha256:a2df7ce4b25d47a79131e2a18af32b9d693eb2cab465da25fa6e4d0dc115644a
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5614444276 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dd8f6a926e3e2eabf9b9c4dc6dd4c63d85383031611ecce8ac9b1cf350a851c3`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:32 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:02:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Mon, 08 Jan 2018 18:01:18 GMT
ENV GIT_VERSION=2.11.1
# Mon, 08 Jan 2018 18:01:19 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Mon, 08 Jan 2018 18:01:20 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Mon, 08 Jan 2018 18:01:20 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Mon, 08 Jan 2018 18:03:57 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Mon, 08 Jan 2018 18:03:58 GMT
ENV GOPATH=C:\gopath
# Mon, 08 Jan 2018 18:05:10 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Mon, 08 Jan 2018 18:05:11 GMT
ENV GOLANG_VERSION=1.10beta1
# Mon, 08 Jan 2018 18:13:30 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'ff2789b7baf33f87111d30bac81ac1ae19dcc16bdd75553f9b5aceda14733a40'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Mon, 08 Jan 2018 18:13:32 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:449343c9d7e2919413898dc8a7e8780ef164b76a3b9dd19de104706edf05113a`  
		Last Modified: Thu, 04 Jan 2018 20:07:32 GMT  
		Size: 1.3 GB (1304019288 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c86d0434e36d69287bea586f96045245d5ee4f04e4e2a5edf6881dbbfdc628c3`  
		Last Modified: Fri, 05 Jan 2018 10:13:30 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cb835a765d1adacc5e96f2684f32ef89614ccc4d5a99be32392b6b52c76ef46`  
		Last Modified: Mon, 08 Jan 2018 19:48:22 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18f729550b3a7040ef71bf29aa3501c84f3dfb64ad061c41bc8d4a677a35cfdf`  
		Last Modified: Mon, 08 Jan 2018 19:48:21 GMT  
		Size: 1.2 KB (1152 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d5421de1bee383e26bb9d4cab7e7f0991622bf7e7047bf93b7bebb8d8ac3354`  
		Last Modified: Mon, 08 Jan 2018 19:48:19 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:680789f514fca4d05e20d2d49441bcb41dca2764a32a068b031fb7c851953342`  
		Last Modified: Mon, 08 Jan 2018 19:48:20 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f7cac87c32591a7d201306b0f43d796071ecc6c2b11da97fa7b0a4a98203df9`  
		Last Modified: Mon, 08 Jan 2018 19:48:35 GMT  
		Size: 29.3 MB (29339650 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:081d4b636d0574daf16ae2a105d7b8b006786307281e608588ca203c00384996`  
		Last Modified: Mon, 08 Jan 2018 19:48:16 GMT  
		Size: 1.2 KB (1175 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5d13313d01fe0e86343cdb272e265f9c10515bc522bdd3d8cb816c4b212f8a4`  
		Last Modified: Mon, 08 Jan 2018 19:48:18 GMT  
		Size: 4.9 MB (4874878 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84502c733d0d40490a59937f30cf8236bc754b54558d5fd082e948e80e812a05`  
		Last Modified: Mon, 08 Jan 2018 19:48:16 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e18e4d5b042fbfe930909365087a712afdd65d7e2476cc7886017c8d1945cce2`  
		Last Modified: Mon, 08 Jan 2018 19:51:42 GMT  
		Size: 206.2 MB (206214903 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:17d3850985bf19a7147a4ba1f04c81e96d95288759549cce1d27d716b687ff8c`  
		Last Modified: Mon, 08 Jan 2018 19:48:16 GMT  
		Size: 1.4 KB (1350 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc-windowsservercore` - windows version 10.0.16299.192; amd64

```console
$ docker pull golang@sha256:70934e6ecd850fef23ac4961984eb702a36e804f163c70fcfc96af15a1290c69
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.2 GB (3198814318 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ffb532b858ad6a2fe8bfcb39eb7b6e5ebe6301a86060364b64b5af1801e84f92`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 03 Jan 2018 04:46:54 GMT
RUN Install update 10.0.16299.192
# Mon, 08 Jan 2018 17:27:32 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Mon, 08 Jan 2018 18:14:29 GMT
ENV GIT_VERSION=2.11.1
# Mon, 08 Jan 2018 18:14:29 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Mon, 08 Jan 2018 18:14:30 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Mon, 08 Jan 2018 18:14:31 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Mon, 08 Jan 2018 18:17:07 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Mon, 08 Jan 2018 18:17:08 GMT
ENV GOPATH=C:\gopath
# Mon, 08 Jan 2018 18:17:59 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Mon, 08 Jan 2018 18:18:00 GMT
ENV GOLANG_VERSION=1.10beta1
# Mon, 08 Jan 2018 18:25:57 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'ff2789b7baf33f87111d30bac81ac1ae19dcc16bdd75553f9b5aceda14733a40'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Mon, 08 Jan 2018 18:25:59 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:9f887ccb8077bdc1f1fedd2da6066bb3542c528f5d103b40659ac25785ba4b9b`  
		Last Modified: Fri, 05 Jan 2018 19:38:30 GMT  
		Size: 689.7 MB (689720734 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:189c9822c1fc60043703fa16f44b1cab80d3a786d35bd6b61628d2b3f1fb9635`  
		Last Modified: Mon, 08 Jan 2018 17:34:16 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ced016f882f58828f852af028c896ce147bb2b33b9d342b64f73d45720ceedd0`  
		Last Modified: Mon, 08 Jan 2018 19:52:05 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f21f168317cdc3c152749d966c0d43db4dc3535f9351d98dacdf0413afbcd7d`  
		Last Modified: Mon, 08 Jan 2018 19:52:04 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfe305114696325373272c3f912e5ca4de2484a6c7534b892c4dea4b2ee5cae2`  
		Last Modified: Mon, 08 Jan 2018 19:52:03 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d6f37549f027d7629c2b600fc88dff293377dd5580bea22e016dcd849122f76`  
		Last Modified: Mon, 08 Jan 2018 19:52:01 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4655597d458099c45393834ed3bc33872b30b343ad2e0477f67472b5c9d1ea22`  
		Last Modified: Mon, 08 Jan 2018 19:52:18 GMT  
		Size: 29.0 MB (28956719 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42e4de5661145bcb63f11eb2c25c9d8b4a03d9ced31d0a6c992ada92bbafbfca`  
		Last Modified: Mon, 08 Jan 2018 19:52:00 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f1ab2305863a8cd8304f89e0d8188b1072315a48130bb54bd5976fee044423f`  
		Last Modified: Mon, 08 Jan 2018 19:52:00 GMT  
		Size: 4.5 MB (4476553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e02f255850155f25292a357fadbc56f682055dd0dd1de721d9d4a1a1cca606e4`  
		Last Modified: Mon, 08 Jan 2018 19:51:58 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d92e8f66c534def927c8a9026c5d527cdf257c1ba9ff1b8dabc0cdff1e2e64e`  
		Last Modified: Mon, 08 Jan 2018 19:55:24 GMT  
		Size: 201.4 MB (201350008 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b845e729726a7b26e929a7d59a40117f0d7ffe06607768efab4be82fac614736`  
		Last Modified: Mon, 08 Jan 2018 19:51:58 GMT  
		Size: 1.3 KB (1348 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
