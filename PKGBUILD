# $Id: PKGBUILD 59294 2009-11-21 20:34:51Z jgc $
# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=ipod-sharp
pkgver=0.8.5
pkgrel=1
pkgdesc="C# bindings for libipoddevice"
arch=('i686' 'x86_64')
license=('GPL')
url="http://download.banshee-project.org/ipod-sharp/"
depends=('podsleuth' 'ndesk-dbus-glib' 'gtk-sharp-2')
options=(!makeflags)
source=(http://download.banshee-project.org/${pkgname}/${pkgver}/${pkgname}-${pkgver}.tar.bz2)
sha256sums=('7c5b02872c75a7d61662e266e6f7a2a1aae14f71d9820a59faef2813dcd825fd')

build() {
  export MONO_SHARED_DIR="${srcdir}/.wabi"
  mkdir -p "${MONO_SHARED_DIR}"

  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr --disable-docs || return 1
  make || return 1
  make DESTDIR="${pkgdir}" install || return 1

  rm -fr "${MONO_SHARED_DIR}"
}
