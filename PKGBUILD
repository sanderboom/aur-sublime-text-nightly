# Maintainer: Sander Boom <sanderboom@gmail.com>

pkgname=sublime-text-nightly
pkgver=3.3111
pkgrel=1
pkgdesc="Sophisticated text editor for code, html and prose - nightly build (available to registered users only)"
arch=('i686' 'x86_64')
url="http://www.sublimetext.com/3dev"
license=('custom')
depends=('libpng' 'gtk2')
optdepends=('gksu: sudo-save support')
conflicts=('sublime-text-dev')
provides=('sublime-text-dev')
install=${pkgname}.install

source=('sublime_text_3.desktop')
source_i686=("https://download.sublimetext.com/sublime_text_3_build_${pkgver:2}_x32.tar.bz2")
source_x86_64=("https://download.sublimetext.com/sublime_text_3_build_${pkgver:2}_x64.tar.bz2")

sha256sums=('3125f8a8db79b4d853a26b0be364ec69a26f3c8e97467ceab09c1b653060f03b')
sha256sums_i686=('c07abc174dbc17519fbe2320e8a1369c7a2a035b66802130061f2a4761f3ddda')
sha256sums_x86_64=('0ed06ea1859cad295866f75a6a0d14c9d7491911d09b1fcaf87744c3c571b3e7')

package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/opt"
  cp --preserve=mode -r "sublime_text_3" "${pkgdir}/opt/sublime_text_3"

  for res in 128x128 16x16 256x256 32x32 48x48; do
    install -dm755 "${pkgdir}/usr/share/icons/hicolor/${res}/apps"
    ln -s "/opt/sublime_text_3/Icon/${res}/sublime-text.png" "${pkgdir}/usr/share/icons/hicolor/${res}/apps/sublime-text.png"
  done

  install -dm755 "${pkgdir}/usr/share/applications"
  install -Dm644 "sublime_text_3.desktop" "${pkgdir}/usr/share/applications/sublime_text_3.desktop"

  install -dm755 "${pkgdir}/usr/bin"
  ln -s "/opt/sublime_text_3/sublime_text" "${pkgdir}/usr/bin/subl3"
}
