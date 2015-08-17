# Maintainer: Daniel Pañeda <dpaneda@gmail.com>
pkgname=picasasync
pkgver=20121114
pkgrel=1
pkgdesc="Sync a directory with your Picasa Web account."
url="https://github.com/placidorevilla/PicasaSync"
arch=(any)
license=('custom:UNLICENSE')
depends=(git python2 googlecl python2-iso8601 pyexiv2 python2-dateutil python2-imaging)
makedepends=(setuptools git python2)
source=()
md5sums=()
_gitroot='git://github.com/dpaneda/PicasaSync.git'
_gitname='PicasaSync'

build() {
    cd $srcdir
  
    msg "Connecting to GIT server..."
    
    if [ -d $_gitname ] ; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone $_gitroot
        cd $_gitname
        python2 setup.py build
    fi

}

package() {
    cd $_gitname
    python2 setup.py install --root=$pkgdir
    install -Dm644 UNLICENSE "$pkgdir/usr/share/licenses/$pkgname/UNLICENSE"
}
