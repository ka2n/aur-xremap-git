# Maintainer: Katsuma Ito <katsumai@gmail.com>

pkgname=xremap-git
pkgver=0.0.3.r35.gcaea9a1
pkgrel=1
pkgdesc="Dynamic key remapper for X Window System"
arch=("any")
url="https://github.com/k0kubun/xremap"
license=("MIT")
depends=("bison" "libx11" "ruby")
makedepends=("git")
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=("git://github.com/k0kubun/xremap")
md5sums=("SKIP")

pkgver() {
	cd "${srcdir}/${pkgname%-git}"

	git describe --tags --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
	cd "${srcdir}/${pkgname%-git}"

	mkdir -p "${pkgdir}/usr/share/licenses/${pkgname%-git}"
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname%-git}/LICENSE"

    make
    mkdir -p "$pkgdir/usr/bin"
    make DESTDIR="$pkgdir/usr/bin" install
}
