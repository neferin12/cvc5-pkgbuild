# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Julian Pollinger <julian@pollinger.dev>
pkgname=cvc5-git
pkgver=1.0.1
pkgrel=2
pkgdesc="cvc5 is a tool for determining the satisfiability of a first order formula modulo a first order theory (or a combination of such theories). "
arch=(x86_64)
url="https://github.com/cvc5/cvc5"
license=('GPLv3')
depends=(libedit libbsd)
makedepends=(git libbsd gcc automake cmake python python-toml jdk-openjdk)
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("git+$url.git#tag=cvc5-1.0.1")
noextract=()
md5sums=('SKIP')


build() {
	cd "cvc5"
	./configure.sh production --auto-download --editline --gpl --cln --prefix="$pkgdir/usr/bin"
	cd build
	make -j$(nproc)
}

package() {
	cd cvc5/build
	make install
}

check() {
	cd cvc5/build
	make check
}
