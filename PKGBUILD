# Maintainer: Giovanni Scafora <giovanni@archlinux.org>
# Contributor: Aaron Griffin <aaron@archlinux.org>

pkgname=parted
pkgver=3.0
pkgrel=2
pkgdesc="A program for creating, destroying, resizing, checking and copying partitions"
arch=('i686' 'x86_64')
license=('GPL3')
url="http://www.gnu.org/software/parted/parted.html"
depends=('device-mapper' 'e2fsprogs')
makedepends=('pkgconfig')
options=('!libtool')
install=${pkgname}.install
source=("http://ftp.gnu.org/gnu/${pkgname}/${pkgname}-${pkgver}.tar.xz")
md5sums=('c415e5c97f86b5ff65a2d925e5a3feb7')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure --prefix=/usr \
              --disable-debug \
              --disable-rpath
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
}
