# Maintainer: Maxime Morel <maxime@mmorel.eu>

pkgname=dali-core-git
pkgver=1.0.41
pkgrel=1
pkgdesc="OpenGl based 3D GUI toolkit - core"
arch=('x86_64' 'i686')
url="git://git.tizen.org/platform/core/uifw/dali-core"
license=('APACHE')
depends=('gcc-libs')
makedepends=('git' 'autoconf')
provides=('dali-core')
conflicts=('dali-core')
source=("git://git.tizen.org/platform/core/uifw/dali-core")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/dali-core"
  printf "%s" "$(git describe | sed -r 's/^dali_(.*)-[0-9]+-[a-z0-9]+$/\1/')"
}

prepare() {
  cd "$srcdir/dali-core"
}

build() {
  cd "$srcdir/dali-core/build/tizen"
  autoreconf --install
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/dali-core/build/tizen"
  make DESTDIR="$pkgdir/" install
}

