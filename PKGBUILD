# Maintainer: Robert Schwarz <mail@rschwarz.net>

pkgname="python2-algebraic"
_pkgname="python-algebraic"
pkgver="0.3.1"
_pkgver="0.3.1.dev-20120112"
pkgrel=1
pkgdesc="Algebraic modeling system for Python"
arch=("any")
url="http://pypi.python.org/pypi/python-algebraic"
license=("GPL")
depends=("python2")
source=("http://pypi.python.org/packages/source/p/${_pkgname}/${_pkgname}-${_pkgver}.zip")
md5sums=()

package() {
  cd "$srcdir/${_pkgname}-${_pkgver}"
  python setup.py install --root="$pkgdir/" --optimize=1
}
