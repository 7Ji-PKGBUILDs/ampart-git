# Maintainer: 7Ji <pugokughin@gmail.com>

pkgname=ampart-git
pkgver=0.1.1.r69.8b9fdb6
pkgrel=1
pkgdesc="A partition tool to modify Amlogic's proprietary eMMC partition format and FDT"
arch=('x86_64' 'aarch64')
url="https://github.com/7Ji/ampart"
license=('GPL3')
depends=('glibc' 'zlib')
makedepends=('git' 'gcc')
source=(
    "ampart::git+${url}.git"
)
sha256sums=(
    'SKIP'
)

pkgver() {
    cd "${srcdir}"/ampart
    printf "%s" "$(git describe --tags | sed 's/^v//;s/\([^-]*-\)g/r\1/;s/-/./g')"
}

build() {
    cd "${srcdir}"/ampart
    make clean
    make
}

package() {
    install -Dm755 "${srcdir}"/ampart/ampart -t "${pkgdir}"/usr/bin/
}