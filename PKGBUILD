# Maintainer: Chirantan Ekbote <chirantan.ekbote at gmail.com>
# Contributor: Kringel
# This PKGBUILD is a modified version of eigen 2.x in extra/eigen

pkgname=eigen3
pkgver=3.2.0
pkgrel=1
pkgdesc="Lightweight C++ template library for vector and matrix math, a.k.a. linear algebra."
arch=('any')
url='http://eigen.tuxfamily.org'
license=('MPL2')
makedepends=('cmake' 'pkg-config')
optdepends=('qt4: for example programs'
    'superlu: optional backend'
    'scotch: optional backend'
    'metis: optional backend')
source=("${pkgname}-${pkgver}.tar.bz2::http://bitbucket.org/eigen/eigen/get/${pkgver}.tar.bz2")
sha1sums=('97de9df52c035dd260ccee6cf6ab09bb559fa441')

build() {
	mkdir -p build
	cd build
	cmake ../eigen-eigen-* \
		-DCMAKE_BUILD_TYPE=Release \
		-DCMAKE_INSTALL_PREFIX=/usr
}

package() {
	cd build
	make DESTDIR="$pkgdir" install
	install -Dm644 ../eigen-eigen-*/COPYING.MPL2 "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
