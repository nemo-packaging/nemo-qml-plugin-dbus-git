## $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=nemo-qml-plugin-dbus-git
pkgver=2.1.21.r0.g861d8e1
pkgrel=1
pkgdesc="DBus plugin for Nemo Mobile"
arch=('x86_64' 'aarch64')
url="https://git.sailfishos.org/mer-core/nemo-qml-plugin-dbus"
license=('BSD-3-Clause' 'LGPL-2.1-only')
depends=('nemo-keepalive')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://git.sailfishos.org/mer-core/nemo-qml-plugin-dbus.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/${pkgname%-git}"
	qmake
	make
}

package() {
	cd "$srcdir/${pkgname%-git}"
	make INSTALL_ROOT="$pkgdir/" install
}
