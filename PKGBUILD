# Maintainer: Maxime Gauduin <alucryd@gmail.com>
# Contributor: Ner0 <darkelfdarkelf666@yahoo.co.uk>

pkgname=pantheon-notify-bzr
pkgver=r27
pkgrel=1
pkgdesc='The Pantheon Notification Daemon'
arch=('i686' 'x86_64')
url='https://launchpad.net/pantheon-notify'
license=('GPL3')
depends=('clutter-gtk' 'granite' 'libwnck3')
makedepends=('bzr' 'cmake' 'vala')
provides=("${pkgname%-*}")
conflicts=("${pkgname%-*}")
source=('bzr+lp:pantheon-notify')
md5sums=('SKIP')

pkgver() {
  cd ${pkgname%-*}

  printf "r%s" "$(bzr revno)"
}

build() {
  cd ${pkgname%-*}

  if [[ -d build ]]; then
    rm -rf build
  fi
  mkdir build && cd build

  cmake .. -DCMAKE_INSTALL_PREFIX='/usr'
  make
}

package() {
  cd ${pkgname%-*}/build

  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
