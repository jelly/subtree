# $Id: PKGBUILD,v 1.31 2007/08/12 08:52:55 aaron Exp $
# Maintainer: Aaron Griffin <aaron@archlinux.org>
# Contributor: dorphell <dorphell@archlinux.org>

pkgname=parted
pkgver=1.8.8
pkgrel=1
pkgdesc="A program for creating, destroying, resizing, checking and copying partitions"
arch=(i686 x86_64)
license=('GPL3')
url="http://www.gnu.org/software/parted/parted.html"
depends=('e2fsprogs')
source=(ftp://ftp.gnu.org/pub/gnu/$pkgname/$pkgname-$pkgver.tar.gz parted-1.7.1-fix-seg.patch)
md5sums=('0d494591731082ec57cc18627728124a' '88f3c5b45fdd1d3dce70a1a19bf48481')
options=(!libtool)

build() {
  cd $startdir/src/$pkgname-$pkgver
  #Arch64 fix - still needed?
  [ "$CARCH" = "x86_64" ] &&  patch -Np1 -i ../parted-1.7.1-fix-seg.patch
  ./configure --prefix=/usr --disable-debug --disable-Werror
  make || return 1
  make DESTDIR=$startdir/pkg install
}
