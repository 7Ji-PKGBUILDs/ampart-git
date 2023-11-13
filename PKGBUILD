# Maintainer: 7Ji <pugokughin@gmail.com>

_pkgbase=ampart
pkgname=${_pkgbase}-git
pkgver=1.3.r12.6f90ddd
pkgrel=2
pkgdesc="A partition tool to modify Amlogic's proprietary eMMC partition format and FDT"
arch=('x86_64' 'aarch64')
url="https://github.com/7Ji/${_pkgbase}"
license=('GPL3')
depends=('glibc' 'zlib')
makedepends=('git')
conflicts=("${_pkgbase}")
provides=("${_pkgbase}=${pkgver}")
source=(
  "${_pkgbase}::git+https://github.com/7Ji/${_pkgbase}.git"
)
sha256sums=(
  'SKIP'
)

pkgver() {
  printf "%s" "$(git --git-dir "${_pkgbase}/.git" describe --tags | sed 's/^v//;s/\([^-]*-\)g/r\1/;s/-/./g')"
}

build() {
  cd "${srcdir}/${_pkgbase}"
  make clean
  make
}

package() {
  install -Dm755 "${srcdir}/${_pkgbase}/${_pkgbase}" -t "${pkgdir}"/usr/bin/
}
