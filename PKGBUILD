# Maintainer: Eric Chu <eric@ericchu.net>
pkgname=homepass
pkgver=1
pkgrel=1
pkgdesc="A simple homepass service"
arch=('any')
url=('https://github.com/ericchu94/homepass')
license=('GPL')
depends=('hostapd')
source=('homepass.conf.example'
        'homepass'
        'homepass@.service')
noextract=()
md5sums=('27c36b67b08316a4487024b57fb39341'
         'f80fbab8fef303e1a49658bd3488b7f4'
         'c30d5402f39d4b0e2c16d008f23acdc3')

package() {
  mkdir -p $pkgdir/etc/homepass/
  cp homepass.conf.example $pkgdir/etc/homepass/

  mkdir -p $pkgdir/usr/bin/
  cp homepass $pkgdir/usr/bin/

  mkdir -p $pkgdir/usr/lib/systemd/system/
  cp homepass@.service $pkgdir/usr/lib/systemd/system/
}
