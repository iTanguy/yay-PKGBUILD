# Maintainer: Tucker Boniface <tucker@boniface.tech>
# Maintainer: Jguer <joaogg3@gmail.com>
pkgname="yay-git"
_pkgname="yay"
pkgver=7.885.r0.g2e8d2b4
pkgrel=1
pkgdesc="Yet another yogurt. Pacman wrapper and AUR helper written in go. (development version)"
arch=('i686' 'x86_64' 'armv7h' 'aarch64')
url="https://github.com/Jguer/yay"
license=('GPL')
options=('!strip' '!emptydirs')
depends=('pacman>=5.1' 'git' 'sudo')
makedepends=('go')
conflicts=('yay-bin' 'yay')
provides=('yay')
source=("yay::git+https://github.com/Jguer/yay.git#branch=master")
md5sums=("SKIP")

pkgver() {
  cd "$srcdir/$_pkgname"
  git describe --long --tags | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "$srcdir/$_pkgname"
  make VERSION=$pkgver
}

package() {
  cd "$srcdir/$_pkgname"
  make VERSION=$pkgver DESTDIR="$pkgdir" install
}
