# Contributer: giacomogiorgianni@gmail.com 

pkgname=lavape
_name=LavaPE
pkgver=0.9.3
pkgrel=1
pkgdesc="is a programming environment for the experimental object-oriented programming language Lava"
arch=(i686 x86_64)
url="http://sourceforge.net/projects/lavape/?source=navbar"
license=('GPL')
depends=('qt4')
source=("http://sourceforge.net/projects/$pkgname/files/LavaPE%20(Windows_Unix)/$pkgname-$pkgver/$pkgname-$pkgver-src.tar.bz2" "$pkgname-start")
md5sums=('795300bf3aa251750c4bbb7aa4964b16' 'a832806f5fd108cbecc9dba1f1601403')

build() {
  cd "$srcdir/${pkgname}"

  qmake-qt4 $pkgname.pro -r -config release \
    "CONFIG+=LINUX_INTEGRATED" \
    "INSTALL_ROOT_PATH=$pkgdir/opt/" \
    "LOWERED_APPNAME=$pkgname"
  make
  
  install -d $pkgdir/opt/$pkgname/{bin,data,doc,samples}
  install -d $pkgdir/usr/{bin,lib}
  install -m 0755 $startdir/$pkgname-start $pkgdir/usr/bin/$pkgname
  cp  -r $srcdir/${pkgname}/lib $pkgdir/usr
  cp  -r $srcdir/${pkgname}/{bin,doc,samples} $pkgdir/opt/$pkgname
  cp $srcdir/${pkgname}/{COPYING,ReleaseNotes,GPL}.txt $pkgdir/opt/$pkgname
  #make INSTALL_ROOT=${pkgdir}  BIN_DIR="${pkgdir}/opt/lavape/" DATA_DIR="${pkgdir}/usr/share/lavape/" install
  #rm -rf /opt/lavape
}