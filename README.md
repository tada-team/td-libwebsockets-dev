![.deb build](https://github.com/tada-team/td-libwebsockets-dev/workflows/build/badge.svg)

td-libwebsockets-dev.deb builder

## Build instructions (on Ubuntu)

1. Clone this repository
1. Get the source archive: `wget 'https://github.com/warmcat/libwebsockets/archive/refs/tags/v3.2.2.tar.gz' --output-document libwebsockets_3.2.2.orig.tar.gz`
1. Verify hash: `sha256sum --check ./hash.txt`
1. Create build directory `mkdir ./build`

