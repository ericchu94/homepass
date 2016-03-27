# Maintainer: Eric Chu <eric@ericchu.net>
pkgname=shomepass
pkgver=1
pkgrel=1
pkgdesc='A systemd homepass service'
arch=('any')
url='https://github.com/ericchu94/shomepass'
license=('GPL')
depends=('hostapd')
source=('shomepass.conf.example'
        'shomepass'
        'shomepass.service')
noextract=()
md5sums=('6a39d0024ee9e1aec104d4fe26f8e6d4'
         '8078cb66141afc1868df3a96a1995495'
         '6c60c546e3c116bb2e0f25f596e571e2')

package() {
  mkdir -p $pkgdir/etc/shomepass/
  cp shomepass.conf.example $pkgdir/etc/shomepass/

  mkdir -p $pkgdir/usr/bin/
  cp shomepass $pkgdir/usr/bin/

  mkdir -p $pkgdir/usr/lib/systemd/system/
  cp shomepass.service $pkgdir/usr/lib/systemd/system/
}
