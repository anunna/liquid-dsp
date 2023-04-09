# This file is part of BlackArch Linux ( https://www.blackarch.org/ ).
# See COPYING for license details.

pkgname=liquid-dsp
pkgver=v1.5.0.r2.gd78f5c1a
pkgrel=1
pkgdesc='Digital signal processing library for software-defined radios.'
arch=('x86_64' 'aarch64')
groups=('blackarch' 'blackarch-radio')
url='http://liquidsdr.org'
license=('MIT')
depends=()
optdepends=('fftw: use shared fft library')
makedepends=('git')
source=("git+https://github.com/jgaeddert/$pkgname.git")
sha512sums=('SKIP')

pkgver() {
  cd $pkgname

  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd $pkgname

  ./bootstrap.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname

  make DESTDIR="$pkgdir/" install
}

