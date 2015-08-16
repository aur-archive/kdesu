# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdesu
pkgver=4.99.0
pkgrel=1
pkgdesc='KDE Su'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kdesu'
license=('LGPL')
depends=('kservice' 'kpty')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('6624d209d1dd30d9424c3aecf9cb031a')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
