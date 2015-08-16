# Maintainer: Laurent Carlier <lordheavym@gmail.com>
# Contributor: Fly-away <flyaaway@gmail.com>

pkgname=libomxil-bellagio
pkgver=0.9.3
pkgrel=1
pkgdesc="An opensource implementation of the OpenMAX Integration Layer API"
arch=('i686' 'x86_64')
url="http://omxil.sourceforge.net"
license=('LGPL')
depends=('glibc')
source=("http://downloads.sourceforge.net/project/omxil/omxil/Bellagio%200.9.3/${pkgname}-${pkgver}.tar.gz"
        fedora-fixes.patch)
md5sums=('a1de827fdb75c02c84e55f740ca27cb8'
         'c34f9facf0cf26171c81f2fc3d562ec6')

prepare() {
  cd ${srcdir}/${pkgname}-$pkgver

  # Fixes from fedora repo
  patch -Np1 -i ../fedora-fixes.patch
}

build() {
  cd ${srcdir}/${pkgname}-${pkgver}

  autoreconf -fiv
  ./configure --prefix=/usr --disable-static --docdir=/usr/share/doc/${pkgname}

  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}

  make DESTDIR="${pkgdir}" install
}

