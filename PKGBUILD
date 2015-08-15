# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: David Sugar <dyfet@gnutelephony.org>
pkgname=cape-devtools
pkgver=0.9.0
pkgrel=1
#epoch=
pkgdesc="Build tools that use and offer user mode chroots"
arch=('x86_64' 'i686')
url="http://www.gnutelephony.org"
license=('GPL3')
groups=()
depends=('ucommon>=6.0.0' 'git' 'perl' 'gnupg')
makedepends=('cmake>=2.6.0')
checkdepends=()
optdepends=('rpm-org: rpm packaging support' 
			'createrepo: rpm archiving support' 
			'dpkg: deb packaging support' 
			'xorg-server-xephyr: nested Xserver chroots')
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=cape-devtools.install
changelog=
source=(http://dev.gnutelephony.org/dist/tarballs/$pkgname-$pkgver.tar.gz)
noextract=()
md5sums=('ec88298781860f15e7eff55cba115f59')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	cmake ./ -DCMAKE_INSTALL_PREFIX=/usr
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
	install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
