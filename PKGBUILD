# Maintainer: Nuno Araujo <nuno.araujo@russo79.com>
pkgname=subvein
pkgver=0.74
pkgrel=1
pkgdesc="Free multiplayer action game"
arch=('i686' 'x86_64')
url="http://subvein.net"
license=('custom')
depends=('unionfs-fuse' 'hicolor-icon-theme' 'xdg-utils')
if [[ "$CARCH" == "x86_64" ]]; then
  depends+=('lib32-glu' 'lib32-libxrandr' 'lib32-freealut')
else
  depends+=('glu' 'libxrandr' 'freealut')
fi
optdepends=()
install=subvein.install
source=("http://subvein.net/downloads/Subvein0740.tar.gz"
        "subvein"
        "subvein-server"
        "subvein.service"
        "etc_confd_subvein"
        "subvein-16x16.png"
        "subvein-24x24.png"
        "subvein-32x32.png"
        "subvein-48x48.png"
        "subvein-64x64.png"
        "subvein.desktop")
md5sums=('8dcef3d074f58e84f979188ef2335502'
         'baedf17366b691de23a31279b3b2c6d8'
         'c0d026ac30413b16e10b480b124a6df3'
         'a428abba505e6b1be1c4de207c62f89b'
         'f12aed37331001110bfc77722d5728fd'
         '146240abe45b133a5c5ea2c0fdd17b7d'
         'cac9d34ccd69e207d14e55aa28a0d280'
         '64058b1043f76a92e8da3cfad4345f66'
         '1a806f08c1d728528bfcb546ba390dba'
         '967ba3a3dbf9db02037275ea36b64b19'
         '576d2feed905444c55849286227d10be')

package() {
  mkdir -p $pkgdir/opt/subvein
  cp -r $srcdir/Subvein/. $pkgdir/opt/subvein
  rm -rf $pkgdir/opt/subvein/lib
  chmod -R g+w $pkgdir/opt/subvein/data
  
  install -m 755 -D $srcdir/subvein $pkgdir/usr/bin/subvein
  install -m 755 -D $srcdir/subvein-server $pkgdir/usr/bin/subvein-server
  install -m 644 -D $srcdir/subvein.service $pkgdir/usr/lib/systemd/system/subvein.service
  install -m 644 -D $srcdir/etc_confd_subvein $pkgdir/etc/conf.d/subvein
  install -m 644 -D $srcdir/subvein-16x16.png $pkgdir/usr/share/icons/hicolor/16x16/apps/subvein.png
  install -m 644 -D $srcdir/subvein-24x24.png $pkgdir/usr/share/icons/hicolor/24x24/apps/subvein.png
  install -m 644 -D $srcdir/subvein-32x32.png $pkgdir/usr/share/icons/hicolor/32x32/apps/subvein.png
  install -m 644 -D $srcdir/subvein-48x48.png $pkgdir/usr/share/icons/hicolor/48x48/apps/subvein.png
  install -m 644 -D $srcdir/subvein-64x64.png $pkgdir/usr/share/icons/hicolor/64x64/apps/subvein.png
  install -m 644 -D $srcdir/subvein.desktop $pkgdir/usr/share/applications/subvein.desktop
  install -m 755 -d $pkgdir/var/lib/subvein
}

# vim:set ts=2 sw=2 et:
