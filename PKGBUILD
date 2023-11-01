# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Dylan Morgan <dbmorgan98@gmail.com>
pkgname=emacs
pkgver=29.1
pkgrel=1
epoch=
pkgdesc=""
arch=()
url=""
license=('GPL')
groups=()
depends=()
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("$pkgname-$pkgver.tar.gz"
        "$pkgname-$pkgver.patch")
noextract=()
md5sums=()
validpgpkeys=()

prepare() {
	cd "$pkgname-$pkgver" || exit
	mkdir build
}

build() {
	cd "$pkgname-$pkgver/build" || exit
	../configure --with-x-toolkit=gtk3 --with-imagemagick --with-json --with-tree-sitter --with-xwidgets --with-file-notification=yes --with-mailutils --with-native-compilation CFLAGS="-march=native -ftree-vectorize -O2 -pipe"
	make
}

check() {
	cd "$pkgname-$pkgver" || exit
	make check
}

package() {
	cd "$pkgname-$pkgver" || exit
	sudo make install
}
