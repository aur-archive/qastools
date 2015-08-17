# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=qastools
pkgver=0.17.2
pkgrel=2
pkgdesc="A collection of desktop applications for the Linux sound system ALSA."
arch=(i686 x86_64)
url="http://www.xwmw.org/qastools/"
license=('GPL3')
depends=('qt4')
makedepends=('cmake')
provides=("qasmixer=$pkgver" "qashctl=$pkgver" "qasconfig=$pkgver")
conflicts=('qasmixer' 'qashctl' 'qasconfig')
install="$pkgname.install"
source=("http://downloads.sourceforge.net/project/$pkgname/$pkgver/${pkgname}_$pkgver.tar.xz")
md5sums=('54792730644ef1d6f23f51d47e8b4ba3')

build() {
  cd "$srcdir/${pkgname}_$pkgver"

  [ -d bld ] || mkdir bld && cd bld
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir/${pkgname}_$pkgver/bld"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
