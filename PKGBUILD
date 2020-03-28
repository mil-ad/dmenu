pkgname=dmenu-milad
pkgver=4.9.db6093f
pkgrel=1
pkgdesc='Generic menu for X'
url='https://github.com/mi-lad/dmenu'
arch=('x86_64')
license=('MIT')
depends=('sh' 'libxinerama' 'libxft' 'freetype2')
source=(git+$url)
md5sums=('SKIP')
sha256sums=('SKIP')
provides=(dmenu)
conflicts=(dmenu)
makedepends=(git)

build() {
  cd dmenu
  make \
          X11INC=/usr/include/X11 \
          X11LIB=/usr/lib/X11 \
          FREETYPEINC=/usr/include/freetype2
}

package() {
  cd dmenu
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm 644 LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}"
}