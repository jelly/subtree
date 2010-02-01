# Maintainer: Aaron Griffin <aaron@archlinux.org>
# Contributor: Giovanni Scafora <giovanni@archlinux.org>

pkgname=parted
pkgver=2.1
pkgrel=1
pkgdesc="A program for creating, destroying, resizing, checking and copying partitions"
arch=('i686' 'x86_64')
license=('GPL3')
url="http://www.gnu.org/software/parted/parted.html"
depends=('device-mapper' 'e2fsprogs')
options=('!libtool')
install=parted.install
source=(ftp://ftp.gnu.org/pub/gnu/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('c0fd26f12fefb013d77cc5160722ec03')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure --prefix=/usr \
              --disable-debug \
              --disable-rpath \
              --disable-Werror || return 1

  make || return 1
  make DESTDIR="${pkgdir}" install || return 1
}
