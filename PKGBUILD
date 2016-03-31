# $Id: PKGBUILD 218178 2014-07-25 22:02:33Z bluewind $
# Maintainer: Leonard König <leonard.r.koenig@gmail.com>
# Contributor: Florian Pritz< flo@xinu.at>
# Contributor: Dany Martineau <dany.luc.martineau@gmail.com>

_pkgname=qrencode
pkgname=lib32-qrencode
pkgver=3.4.4
pkgrel=1
pkgdesc="C library for encoding data in a QR Code symbol."
arch=(i686)
depends=('lib32-libpng')
makedepends=(sdl)
url="http://megaui.net/fukuchi/works/qrencode/index.en.html"
license=('GPL')
source=(http://megaui.net/fukuchi/works/${_pkgname}/${_pkgname}-${pkgver}.tar.bz2)
md5sums=('62ba472bede0ad393cc63e0012b5f007')

build() {
  cd "${srcdir}/$_pkgname-$pkgver"

  export CC="gcc -m32"
  export CXX="g++ -m32"
  export PKG_CONFIG_PATH="/usr/lib32/pkgconfig"

  ./configure \
	  --prefix=/usr \
	  --libexecdir=/usr/lib32 \
	  --libdir=/usr/lib32

  make
}

package() {
  cd "${srcdir}/$_pkgname-$pkgver"

  make DESTDIR="$pkgdir" install

  rm -rf "${pkgdir}"/usr/{bin,include,lib,share}
}
