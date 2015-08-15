pkgname=gl3n-git
pkgver=20120623
pkgrel=1
pkgdesc='OpenGL Maths for D (not glm for D but better).'
arch=(i686 x86_64)
url='https://github.com/Dav1dde/gl3n'
license=('MIT')
makedepends=('git')
provides=('gl3n')
md5sums=()

_gitroot="https://github.com/Dav1dde/gl3n.git"
_gitname="gl3n"

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi
  
  msg 'Running make'

  make PREFIX=/usr
  mkdir -p $pkgdir/usr
  make install PREFIX=$pkgdir/usr
}
