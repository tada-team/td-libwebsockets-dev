![.deb build](https://github.com/tada-team/td-libwebsockets-dev/workflows/build/badge.svg)

td-libwebsockets-dev.deb builder

## Build instructions (on Ubuntu)

1. Clone this repository
1. Get the source archive: `wget 'https://github.com/warmcat/libwebsockets/archive/refs/tags/v3.2.2.tar.gz' --output-document libwebsockets_3.2.2.orig.tar.gz`
1. Verify hash: `sha256sum --check ./hash.txt`
1. Extract source `tar --extract --file libwebsockets_3.2.2.orig.tar.gz`
1. Create build directories `cp -r ./libwebsockets-3.2.2 ./build_amd64` `cp -r ./libwebsockets-3.2.2 ./build_arm64`
1. Copy debian directory `cp -r ./debian ./build_amd64` `cp -r ./debian ./build_arm64`
1. Add ARM64 architecture `sudo dpkg --add-architecture arm64`
1. Update sources.list `cat ./bionic-sources.txt | sudo tee /etc/apt/sources.list `
1. Update package list `sudo apt update`
1. Install build dependencies `sudo apt install binutils-aarch64-linux-gnu build-essential crossbuild-essential-arm64 devscripts debhelper cmake libcap-dev libev-dev libssl-dev libuv1-dev openssl zlib1g-dev`
1. Instal ARM64 dependencies `sudo apt install libcap-dev:arm64 libev-dev:arm64 libssl-dev:arm64 libuv1-dev:arm64 zlib1g-dev:arm64`
1. Build AMD64 `cd ./build_amd64` `debuild --unsigned-source --unsigned-buildinfo --unsigned-changes`
1. Build ARM64 `cd ./build_arm64` `debuild -aarm64 --unsigned-source --unsigned-buildinfo --unsigned-changes`

