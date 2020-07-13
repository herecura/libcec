# Maintainer: BlackIkeEagle <ike DOT devolder AT gmail DOT com>
# Contributor: Philippe Cherel <philippe.cherel@mayenne.org>
# vim: ft=sh:

pkgname=libcec
pkgver=6.0.2
pkgrel=1
pkgdesc="Pulse-Eight's libcec for the Pulse-Eight USB-CEC adapter"
arch=('x86_64')
url="http://libcec.pulse-eight.com/"
license=('GPL')
makedepends=('cmake')
depends=('udev' 'p8-platform' 'libxrandr')
source=("$pkgname-$pkgver.tar.gz::https://github.com/Pulse-Eight/$pkgname/archive/$pkgname-$pkgver.tar.gz")
sha256sums=('090696d7a4fb772d7acebbb06f91ab92e025531c7c91824046b9e4e71ecb3377')

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
