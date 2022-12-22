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
            '71f6ed5746648375cebba5fbeb20f99cc9ae5b88b56ad61f5a63fece60c1f258')
b2sums=('0474c47f592751e117ecad40c26e8c2cc445e85336cf4ae4807a0ed8546d637e6c9050afd3621368d48c2828db84558b18e48de7b37ba7973fb08deac29a2386'
        'bc88c287b1c698102d66e55ca6e7ac3a0fe858ff2f482c9e93f53810b62603c166e928cc2aaf5925977feb7469fc1ba27601fca08f6e216337cd07b30e0d285c')
