pkgname=sflock
pkgver=$(grep "^VERSION" config.mk  | awk '{ print $3 }')
pkgrel=1
pkgdesc="A simple screen locker for X"
arch=('i686' 'x86_64')
url="https://github.com/benruijl/sflock"
license=('MIT')
depends=('libxext' 'ttf-dejavu')
makedepends=('git')
source=()
#source=('git+https://github.com/benruijl/sflock.git')
#sha256sums=('SKIP')

prepare() {
  cd "$startdir"
  echo "$startdir $srcdir/$pkgname"
}


build() {
  cd "$startdir"
  #cd "$pkgname"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd "$startdir"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
