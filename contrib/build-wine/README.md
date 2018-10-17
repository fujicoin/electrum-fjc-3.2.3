Windows Binary Builds
=====================

These scripts can be used for cross-compilation of Windows Electrum executables from Linux/Wine.

For reproducible builds, see the `docker` folder.


Usage:


1. Install the following dependencies:

 - dirmngr
 - gpg
 - 7Zip
 - Wine (>= v2)
 - (and, for building libsecp256k1)
   - mingw-w64
   - autotools-dev
   - autoconf
   - libtool


For example:

```
sudo su -
apt-get install wine-development dirmngr gnupg2 p7zip-full
apt-get install mingw-w64 autotools-dev autoconf libtool
```

2. Compile

```
git clone https://github.com/fujicoin/electrum-fjc.git 
cd electrum-fjc/contrib/build-wine
./build-secp256k1.sh
./prepare-wine.sh
./build-electrum-git.sh
```

The generated binaries are in `./dist`.
