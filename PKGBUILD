# Maintainer: Maxime Gauduin <alucryd@archlinux.org>

pkgname=switchboard-plug-user-accounts
pkgver=0.1.4
pkgrel=1
pkgdesc='User Accounts plug for Switchboard'
arch=('i686' 'x86_64')
url='https://launchpad.net/switchboard-plug-useraccounts'
license=('GPL3')
groups=('pantheon')
depends=('accountsservice' 'cairo' 'gdk-pixbuf2' 'glib2' 'glibc'
         'gnome-desktop' 'gtk3' 'libgee' 'libpwquality' 'polkit'
         'libgranite.so' 'libswitchboard-2.0.so')
makedepends=('cmake' 'switchboard' 'vala')
source=("https://launchpad.net/switchboard-plug-useraccounts/loki/${pkgver}/+download/switchboard-plug-useraccounts-${pkgver}.tar.xz")
sha256sums=('cf0c2cea9514f30f4c67ba7327c0f03c3f0bd3de063bb1c2789c412a6d1f6ad6')

prepare() {
  cd switchboard-plug-useraccounts-${pkgver}

  if [[ -d build ]]; then
    rm -rf build
  fi
  mkdir build
}

build() {
  cd switchboard-plug-useraccounts-${pkgver}/build

  cmake .. \
    -DCMAKE_BUILD_TYPE='Release' \
    -DCMAKE_INSTALL_PREFIX='/usr' \
    -DCMAKE_INSTALL_LIBDIR='/usr/lib'
  make
}

package() {
  cd switchboard-plug-useraccounts-${pkgver}/build

  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
