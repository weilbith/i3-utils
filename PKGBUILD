# shellcheck disable=SC2034

pkgname='i3-utils'
pkgrel=1
pkgver=1
pkgdesc="Utility script for the i3 window manager"
arch=('any')
url="https://github.com/weilbith/i3-utils.git"
license=('MIT')
depends=('i3lock-color')
optdepends=('dmenu: user selection' 'rofi: better dmenu alternative')
makedepends=('git')
source=("$pkgname::git+https://github.com/weilbith/i3-utils#branch=master")
sha256sums=('SKIP')

pkgver() {
  cd "$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  install -Dv -t "$pkgdir/usr/bin/" "$srcdir/$pkgname/"{i3-goto-mark,i3-win-info,i3-lock}
}
