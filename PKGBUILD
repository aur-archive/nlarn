# Maintainer: Joao Cordeiro <jlcordeiro at gmail dot com>
pkgname=nlarn
pkgver=0.7.2
pkgrel=2
pkgdesc="A rewrite of Larn that tries to improve the gameplay by using state-of-the-art roguelike technology and a simplified user interface."
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/nlarn/"
license=('GPL3')
depends=('glib2' 'lua' 'zlib')
makedepends=()
source=(http://sourceforge.net/projects/nlarn/files/nlarn/$pkgver/nlarn-$pkgver.tar.gz
        nlarn.sh)
md5sums=('3a1ffa3077677818081f4ad4eb0a9fdf'
         'e154579fd87af4ca708c8b3b4c565839')

build() {
    cd "$srcdir/nlarn-$pkgver"

  sed s/ncurses5-config/ncursesw5-config/g -i Makefile

  make config=release nlarn

  _dest_dir="$pkgdir/usr/share/nlarn"
  mkdir -p $_dest_dir/lib

  install -D -m 644 lib/* "$_dest_dir/lib/"
  install -D -m 755 nlarn "$_dest_dir/nlarn"
  install -T -D -m 755 $srcdir/nlarn.sh $pkgdir/usr/bin/nlarn
}

# vim:set ts=2 sw=2 et:
