# Maintainer: sharow <shirowmiura at gmail dot com>

pkgname=seq2gif-git
_pkgver=0.10.3
pkgver=0.10.3.182.253dacb
pkgrel=1
pkgdesc="Convert a ttyrec record into a gif animation directly"
arch=('i686' 'x86_64')
url="https://github.com/saitoha/seq2gif"
license=('GPL' 'custom')
depends=()
makedepends=('git')
conflict=('')
source=("$pkgname"::'git+https://github.com/saitoha/seq2gif.git#tag=v0.10.3')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  local count="$(git rev-list --count --all master)"
  local rev="$(git rev-parse --short master)"
  echo "$_pkgver.$count.$rev"
}

build() {
  cd $pkgname
  ./configure --prefix=/usr
  make
}

check() {
  cd $pkgname
  make -k check
}

package() {
  cd $pkgname
  make DESTDIR="$pkgdir/" install
}
