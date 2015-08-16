# Maintainer: Ole Erik Brennhagen <oleerik@startmail.com>
# Contributor: Dan Sagunov <danilka.pro@gmail.com>

pkgname=manaplus
pkgver=1.5.5.9
pkgrel=1
builddir=$pkgname-$pkgver
pkgdesc="ManaPlus is a 2D MMORPG game advanced client for games based on eAthena fork The Mana World (tAthena) also for other forks like Evol."
arch=('i686' 'x86_64')
source=(http://download.evolonline.org/manaplus/download/1.5.5.9/manaplus-1.5.5.9.tar.xz)
url="http://manaplus.org"
depends=('libxml2' 'physfs' 'sdl_image' 'sdl_mixer' 'sdl_net' 'sdl_ttf' 'sdl_gfx' 'xsel' 'glu')
conflicts=('manaplus-git')
license=('GPL2')
md5sums=('95bb59b6f729526378a432e652c7026f')
build() {
	cd "$srcdir/$builddir"
	autoreconf -i
	./configure --prefix=/usr
	make clean
	make || return 1
}

package() {
	cd "$srcdir/$builddir"
	make DESTDIR="$pkgdir/" install
}
