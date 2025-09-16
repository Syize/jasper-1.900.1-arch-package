# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Syize <syizeliu@gmail.com>
pkgname='jasper-1.900.1'
pkgname2='jasper'
pkgver=1
pkgrel=1
epoch=
pkgdesc="Self-used jasper to build WRF model."
arch=('x86_64')
url="https://github.com/Syize/jasper/tree/1.900.1"
license=('GPL')
groups=('wrf')
depends=(libjpeg-turbo glibc)
makedepends=(make gcc)
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("${pkgname2}-${pkgver}.tar.gz::https://github.com/Syize/jasper/archive/refs/tags/v1.900.2.tar.gz")
noextract=()
sha256sums=('13f3cab84cc216667030969a68239e2cc806e6445f3a99cf6e76b78bfa5b6162')
validpgpkeys=()

prepare() {
	tar -zxvf ${pkgname2}-${pkgver}.tar.gz
}

build() {
	cd "${pkgname2}-1.900.2"
	./configure --prefix=/usr --enable-shared=yes --libdir=/usr/lib/jasper-1.900.1 --includedir=/usr/include/jasper-1.900.1 CFLAGS="-fpermissive"
	make
}

check() {
	cd "${pkgname2}-1.900.2"
}

package() {
	cd "${pkgname2}-1.900.2"
	make DESTDIR="$pkgdir/" install
}
