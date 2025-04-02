# $Id$
# Maintainer: Chupligin Sergey (NeoChapay) <neochapay@gmail.com>

pkgname=nemo-qml-plugin-fingerprint
pkgver=0.0.3
pkgrel=1
pkgdesc="Nemomobile QML plugin for fprintd"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/nemo-qml-plugin-fingerprint"
license=('LGPL-2.0-or-later')
depends=('qt6-declarative' 'fprintd' 'qt6-base')
makedepends=('cmake' 'qt6-tools')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('d6ba4bd2a4e2c8b9d271dc4add44d4fa36b51e60e91d2524fd9dc9a03452dcb4')

build() {
    cd $pkgname-$pkgver
    cmake -DCMAKE_INSTALL_PREFIX:PATH='/usr'\
          -DCMAKE_POLICY_VERSION_MINIMUM=3.5 .
    make -j1
}

package() {
    cd $pkgname-$pkgver
    make DESTDIR="$pkgdir" install
}
