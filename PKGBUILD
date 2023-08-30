# Maintainer: Nekosis <37462865+Nekosis@users.noreply.github.com>
pkgname='bsp-layout'
pkgver=0.0.10
pkgrel=4
pkgdesc="Manage layouts in bspwm (tall and wide)"
arch=('any')
url="https://github.com/phenax/bsp-layout"
license=('MIT')
depends=('bash' 'bspwm' 'bc' 'man')
makedepends=('git')
source=("$url/archive/$pkgver.tar.gz")
sha256sums=('ec71dd3438ff84ab3dd6d72673500a33158937112e9fcf87c64b02313bc1c1c8')

prepare() {
    cd "$pkgname-$pkgver"
    mv ../../Makefile.new Makefile
}

build() {
	cd "$pkgname-$pkgver"
	make
}

package() {
    cd "$pkgname-$pkgver"
    make DESTDIR="$pkgdir/" PREFIX="/usr" install
}
