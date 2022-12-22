# Maintainer: bcrumb <shadow dot sandlot dot tribute at proton dot me>

pkgname=asahi-scripts
pkgver=20221220
pkgrel=1
pkgdesc='Asahi Linux maintenance scripts'
arch=('any')
url='http://asahilinux.org'
license=('MIT')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/AsahiLinux/${pkgname}/archive/refs/tags/${pkgver}.tar.gz" asahi-scripts.patch)
install=asahi-scripts.install
sha256sums=('cc2b9e2d01972dd9290ca3ca480f1b83101ace760ef45739a5b3588f80653c68')
b2sums=('0474c47f592751e117ecad40c26e8c2cc445e85336cf4ae4807a0ed8546d637e6c9050afd3621368d48c2828db84558b18e48de7b37ba7973fb08deac29a2386')
backup=(etc/m1n1.conf)

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  make PREFIX=/usr DESTDIR=${pkgdir} all
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  make PREFIX=/usr DESTDIR=${pkgdir} install-arch

  install -Dm644 "$srcdir/${pkgname}-${pkgver}/LICENSE" \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

prepare() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  patch --forward --strip=1 --input="${srcdir}/asahi-scripts.patch"
}
sha256sums=('cc2b9e2d01972dd9290ca3ca480f1b83101ace760ef45739a5b3588f80653c68'
            '449f375fc6c9449a4f55aaf82416384b3a0a3312176a8ed78fd7d60c9369005b')
b2sums=('0474c47f592751e117ecad40c26e8c2cc445e85336cf4ae4807a0ed8546d637e6c9050afd3621368d48c2828db84558b18e48de7b37ba7973fb08deac29a2386'
        '3d4bc42a7b2c4c2ead1815b77b23f20b31de2c78610d308b29c071889e5d5dc3e04ae0bf77d0819d39c57200663f469b782d8cfb61955bb7a4a4667dd200f256')
