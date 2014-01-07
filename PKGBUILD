# $Id: pkgbuild-mode.el,v 1.23 2007/10/20 16:02:14 juergen Exp $
# Maintainer: Leif Walsh <leif.walsh@gmail.com>
pkgname=icpld
pkgver=1.1.5
pkgrel=1
pkgdesc="a connection monitor which allows you to keep track of your network connection perfomance."
arch=('i686' 'x86_64')
url="http://www.ibiblio.org/icpld/"
license=('BSD')
groups=()
depends=()
makedepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=(etc/icpld.conf)
options=()
install=icpld.install
changelog=
source=(http://www.ibiblio.org/$pkgname/download/$pkgname-$pkgver.tar.gz
        icpld.service
        icpld.conf)
md5sums=('e6ba14964ee11c20adf6f7f35b62ccb0'
         '3136b2ce2340d5a44a894cc77841fe4d'
         'cbec49385174bd19f8d4acebc73be0cc')
noextract=()

build() {
  cd $startdir/src/$pkgname-$pkgver

  ./configure --prefix=/usr
  make
}

package() {
  cd $startdir/src/$pkgname-$pkgver

  make DESTDIR="$pkgdir" install
  install -Dm644 "$srcdir/icpld.conf" "$pkgdir/etc/icpld.conf"
  install -Dm644 "$srcdir/icpld.service" "$pkgdir/usr/lib/systemd/system/icpld.service"
}

# vim:set ts=2 sw=2 et:
