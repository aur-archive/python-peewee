# Maintainer: Nidhogg
# Contributor: juantascon

pkgname=python-peewee
pkgver=2.5.1
pkgrel=1
pkgdesc="a little orm"
url="https://pypi.python.org/pypi/peewee/"
arch=('any')
license=('MIT')
depends=('python')
makedepends=('python-setuptools')
optdepends=(
	'python-psycopg2: for PostgreSQL database support'
	'mysql-python: for MySQL database support'
	'python-pymysql: for MySQL database support'
	)
source=(http://pypi.python.org/packages/source/p/peewee/peewee-$pkgver.tar.gz)
sha256sums=('c29efa8f84e04cb6e28c568d1bcb0d51cfbc75117fea9b54bfd55f51e341dfb1')

build() {
  cd $srcdir/peewee-$pkgver
  python setup.py build
}

package() {
  cd $srcdir/peewee-$pkgver
  python setup.py install --root=$pkgdir --optimize=1
  install -D -m644 LICENSE $pkgdir/usr/share/licenses/$pkgname/COPYING
  install -D -m644 README.rst $pkgdir/usr/share/$pkgname/README.rst
  install -D -m644 TODO.rst $pkgdir/usr/share/$pkgname/TODO.rst
  cd $pkgdir/usr/bin
}
