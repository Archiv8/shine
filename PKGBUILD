#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [Query]: Last update of shine was 76ea4f0, https://github.com/toots/shine/commit/76ea4f072e03a3d76283c99412f698076a20a362, on 2019/04/19. Latest release was 3.1.1, https://github.com/toots/shine/releases/tag/3.1.1, on 2017/07/28. Is Shine actively maintained
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

pkgname=shine
pkgver=3.1.1
pkgrel=3
pkgdesc="Super fast fixed-point MP3 encoder"
arch=("arm" "i686" "x86_64")
url="https://github.com/savonet/shine"
source=($pkgname-$pkgver.tar.gz::https://github.com/toots/$pkgname/archive/$pkgver.tar.gz)
license=(GPL2)
depends=(
"glibc"
)
makedepends=(
"automake"
"autoconf"
"make"
"libtool"
)
options=(
"!libtool"
"!strip"
)
sha512sums=(
"57b017d22b373507844870ea5837962488f4a0e2238df7b79c837df0aa8f7304ba82d8d7f55d47980b854518f8e34aa55a9fa40f6260650fd7d23f5a94cd4484"
)

build() {
cd "${srcdir}/${pkgname}-${pkgver}"
./bootstrap
./configure --prefix=/usr
make all
}

package() {
cd "${srcdir}/${pkgname}-${pkgver}"
make DESTDIR="${pkgdir}" install
}
