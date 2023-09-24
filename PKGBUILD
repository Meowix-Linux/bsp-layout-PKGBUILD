# Maintainer: Nekosis <37462865+Nekosis@users.noreply.github.com>
pkgname='bsp-layout'
pkgver=0.0.10
pkgrel=6
pkgdesc="Manage layouts in bspwm (tall and wide)"
arch=('any')
url="https://github.com/phenax/bsp-layout"
license=('MIT')
depends=('bash' 'bspwm' 'bc' 'man')
makedepends=('git')
source=("$url/archive/$pkgver.tar.gz" "Makefile.new")
sha256sums=( 'ec71dd3438ff84ab3dd6d72673500a33158937112e9fcf87c64b02313bc1c1c8' 'ebe91be3a1c262352fd74dcd97f1313a51892c5346a3bed1790310dd49da32f1')

prepare() {
    cd "$pkgname-$pkgver"
    mv ../Makefile.new Makefile
}

build() {
	cd "$pkgname-$pkgver"
	make
}

package() {
    cd "$pkgname-$pkgver"
    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    sed -i '4s/.*/export ROOT="\/usr\/lib\/bsp-layout";/' "$pkgdir/usr/lib/bsp-layout/layout.sh"
    ln -sf /usr/lib/bsp-layout/layout.sh $pkgdir/usr/bin/bsp-layout
}
