#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>


pkgname=shine
pkgver=3.1.1
pkgrel=2
pkgdesc='Super fast fixed-point MP3 encoder'
arch=('arm' 'i686' 'x86_64')
url="https://github.com/savonet/shine"
source=($pkgname-$pkgver.tar.gz::https://github.com/toots/$pkgname/archive/$pkgver.tar.gz)
license=(GPL2)
depends=('glibc')
makedepends=('automake' 'autoconf' 'make' 'libtool')
options=('!libtool' '!strip')
sha256sums=('565b87867d6f8e6616a236445d194e36f4daa9b4e7af823fcf5010af7610c49e')
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
