# $Id$
# Maintainer: BlackIkeEagle <ike DOT devolder AT gmail DOT com>
# Contributor: Philippe Cherel <philippe.cherel@mayenne.org>
# vim: ft=sh:

pkgname=libcec
pkgver=4.0.2
pkgrel=1
pkgdesc="Pulse-Eight's libcec for the Pulse-Eight USB-CEC adapter"
arch=('x86_64')
url="http://libcec.pulse-eight.com/"
license=('GPL')
makedepends=('cmake')
depends=('udev' 'lockdev' 'p8-platform' 'libxrandr')
source=("$pkgname-$pkgver.tar.gz::https://github.com/Pulse-Eight/$pkgname/archive/$pkgname-$pkgver.tar.gz")
sha256sums=('b8b8dd31f3ebdd5472f03ab7d401600ea0d959b1288b9ca24bf457ef60e2ba27')

build() {
    cd "$pkgname-$pkgname-$pkgver"
    mkdir build
    cd build
    cmake .. \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBDIR=/usr/lib \
        -DCMAKE_INSTALL_LIBDIR_NOARCH=/usr/lib
    make
}

package() {
    cd "$pkgname-$pkgname-$pkgver/build"
    make DESTDIR="$pkgdir" install
}
