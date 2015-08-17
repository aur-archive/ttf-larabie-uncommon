# Maintainer: TDY <tdy@gmx.com>

pkgname=ttf-larabie-uncommon
pkgver=20011216
pkgrel=2
pkgdesc="An Ubuntu compilation of Ray Larabie's fonts, suited for eccentric and special contexts"
arch=('any')
url="http://www.larabiefonts.com/"
license=('custom')
depends=('fontconfig' 'xorg-font-utils')
install=ttf.install
source=(http://archive.ubuntu.com/ubuntu/pool/multiverse/t/ttf-larabie/ttf-larabie_$pkgver.orig.tar.gz
        $pkgname.list)
md5sums=('007e062811eb34a0f1e702299dbac271'
         '9ddb0339b5782157a039ce7b315d1e76')

package() {
  cd "$srcdir/ttf-larabie-$pkgver"
  install -Dm644 READ_ME.TXT "$pkgdir/usr/share/licenses/$pkgname/license.txt"

  msg2 "Extracting ttf-larabie collection..."
  find -name '*.zip' -exec bsdtar -xf {} \;

  msg2 "Packaging uncommon fonts..."
  install -dm755 "$pkgdir/usr/share/fonts/TTF"
  while read _ttf; do
    find -iname "$_ttf" -exec install -m644 {} "$pkgdir/usr/share/fonts/TTF" \;
  done < ../$pkgname.list
}

# vim:set ts=2 sw=2 et:
