# Maintainer: Aaron Griffin <aaron@archlinux.org>
# Contributor: Giovanni Scafora <giovanni@archlinux.org>

pkgname=parted
pkgver=1.9.0
pkgrel=3
pkgdesc="A program for creating, destroying, resizing, checking and copying partitions"
arch=('i686' 'x86_64')
license=('GPL3')
url="http://www.gnu.org/software/parted/parted.html"
depends=('device-mapper' 'e2fsprogs')
options=('!libtool')
install=parted.install
source=(ftp://ftp.gnu.org/pub/gnu/${pkgname}/${pkgname}-${pkgver}.tar.gz
        parted-1.9.0.patch)
md5sums=('055305bc7bcf472ce38f9abf69a9d94d'
         '0a1622cdca6e161ae2a40083b2d046bd')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  # See http://gparted.sourceforge.net/news.php
  patch -Np1 -i ${srcdir}/parted-1.9.0.patch || return 1

  ./configure --prefix=/usr \
              --disable-debug \
              --disable-rpath \
              --disable-Werror || return 1

  make || return 1
  make DESTDIR="${pkgdir}" install || return 1
}
