# Maintainer epsilonKNOT <epsilon.aur@epsilonKNOT.xyz>

pkgbase=usockets
pkgname=usockets
pkgver=0.7.1
epoch=1
pkgrel=1
pkgdesc="Miniscule cross-platform eventing, networking & crypto for async applications"
url="https://github.com/uNetworking/uSockets"
license=('Apache')
arch=('any')
source=( "https://github.com/uNetworking/uSockets/archive/refs/tags/v${pkgver}.tar.gz" )
sha256sums=('1fdc5376e5ef9acf4fb673fcd5fd191da9b8d59a319e9ec7922872070a3dd21c')
depends=( openssl )

prepare() {
	cd "uSockets-$pkgver"
	patch < ../../usockets-$pkgver-Makefile.patch
}

build() {
	cd "uSockets-$pkgver"
	make VERSION=$pkgver WITH_OPENSSL=1 default
}

package() {
	cd "uSockets-$pkgver"
	make VERSION=$pkgver DESTDIR="$pkgdir/" install
}

#vim: syntax=sh
