pkgname=jpegoptim
pkgver=1.4.3
pkgrel=1
pkgdesc="Jpeg optimisation utility"
arch=('x86_64')
url="http://www.kokkonen.net/tjko/projects.html"
license=('GPL')
depends=('glibc' 'libjpeg')
source=(http://www.kokkonen.net/tjko/src/${pkgname}-${pkgver}.tar.gz)
sha512sums=('4495e9cf5af9ba41273bf23a4abea724adb19ddac373d5985c29fe65b227c0b23bf14baaa28fa8f8617370e9b9fe41b0d365ad19da67f34d32fa857232c7b09e')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure --prefix=/usr
  make
  make strip
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  make prefix="${pkgdir}/usr" install
  install -m 644 -D COPYING ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
}
