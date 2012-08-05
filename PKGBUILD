# Maintainer: Robert Schwarz <mail@rschwarz.net>

pkgname="python2-zibopt"
_pkgname="python-zibopt"
pkgver="0.7.2"
_pkgver="0.7.2.dev-r226"
pkgrel=1
pkgdesc="Python wrapper for the MIP solver SCIP with modeling features."
arch=("i686" "x86_64")
url="https://code.google.com/p/python-zibopt/"
license=("GPL")
depends=("python2" "python2-algebraic" "scipoptsuite")
makedepends=("python2" "python2-algebraic" "scipoptsuite")
source=("https://python-zibopt.googlecode.com/files/${_pkgname}-${_pkgver}.tar.gz"
        "01_scip30.patch"
        "02_warnings.patch"
        "03_libs.patch")
md5sums=()

build() {
  cd "$srcdir/$_pkgname-$_pkgver"

  # fixes to address interface changes in SCIP
  patch -p1 < "$srcdir/01_scip30.patch"

  # fix compiler warnings
  patch -p1 < "$srcdir/02_warnings.patch"

  # additional linker libraries (zlib, readline)
  patch -p1 < "$srcdir/03_libs.patch"

  python2 setup.py build
}

check() {
  cd "$srcdir/$_pkgname-$_pkgver"
  python2 setup.py test
}

package() {
  cd "$srcdir/$_pkgname-$_pkgver"
  python setup.py install --root="$pkgdir/" --optimize=1
}
