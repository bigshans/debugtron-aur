# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Bigshans <wo199710@hotmail.com>
pkgname=Debugtron
pkgver=0.5.0
pkgrel=1
pkgdesc="Debug in-production Electron based app"
arch=("x86_64")
url="https://github.com/bytedance/debugtron"
license=('MIT')
conflicts=()
replaces=()
backup=()
options=()
source=("https://github.com/bytedance/debugtron/releases/download/v${pkgver}/Debugtron-linux-x64-${pkgver}.zip"
        "${pkgname}.desktop")
sha256sums=('6808e728514d1f053bc3c63963cbf549f6e5fcb47220d964b793ac9be6172baf'
            'de156d2d0d3df137bbabb0e030e9c202f2f101f5b6235e71a7caa1a72dcd44d1')

package() {
    install -d "$pkgdir"/opt
    install -d "$pkgdir"/usr/share/applications
    install -Dm644 $srcdir/$pkgname.desktop "$pkgdir"/usr/share/applications/Debugtron.desktop
    cp -R "$srcdir"/Debugtron-linux-x64 "$pkgdir"/opt/Debugtron
    find "$pkgdir"/opt/Debugtron -type f -exec chmod 664 {} \;
    chmod 755 "$pkgdir"/opt/Debugtron/Debugtron
    chmod 4755 "$pkgdir"/opt/Debugtron/chrome-sandbox
}
