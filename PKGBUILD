# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-adsp-freesurround
_commit=0b6bc04
pkgver=20161031.0b6bc04
pkgrel=1
pkgdesc="FreeSurround AudioDSP add-on for Kodi"
arch=('i686' 'x86_64')
url='https://github.com/kodi-adsp/adsp.freesurround'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-adsp')
depends=('kodi-platform')
makedepends=('git' 'cmake')
source=("$pkgname::git://github.com/kodi-adsp/adsp.freesurround.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$pkgname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}

