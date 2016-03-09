# Maintainer: Eric Chu <eric@ericchu.net>
pkgname=homepass
pkgver=1
pkgrel=1
pkgdesc='A simple homepass service'
arch=('any')
url='https://github.com/ericchu94/homepass'
license=('GPL')
depends=('hostapd')
source=('homepass.conf.example'
        'homepass'
        'homepass@.service')
noextract=()
md5sums=('82f8defb0650162c6b8653b4088cd262'
         '8078cb66141afc1868df3a96a1995495'
         'c30d5402f39d4b0e2c16d008f23acdc3')

package() {
  mkdir -p $pkgdir/etc/homepass/
  cp homepass.conf.example $pkgdir/etc/homepass/

  mkdir -p $pkgdir/usr/bin/
  cp homepass $pkgdir/usr/bin/

  mkdir -p $pkgdir/usr/lib/systemd/system/
  cp homepass@.service $pkgdir/usr/lib/systemd/system/
}
