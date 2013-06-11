# Maintainer: Jason Axelson <jason.axelsonATgmail.com>
# Contributor: Sean Escriva <sean.escrivaATgmail.com>
# Contributor: William Ting <william.h.tingATgmail.com>

# vim:set ts=4 sw=4 et:

pkgname=autojump-git
pkgver=20130610
pkgrel=1
pkgdesc="A faster way to navigate your filesystem from the command line"
arch=(any)
url="http://github.com/joelthelion/autojump"
license=('GPL3')
depends=('bash' 'python')
makedepends=('git')
conflicts=('autojump')
provides=('autojump')
replaces=()
backup=()
source=()
md5sums=()

_gitroot="git://github.com/joelthelion/autojump.git"
_gitname="autojump"

build() {
    msg "connecting to git server..."

    if [ -d ${srcdir}/${_gitname} ]; then
        cd ${srcdir}/${_gitname} && git pull origin
    else
        git clone ${_gitroot} ${srcdir}/${_gitname}
    fi

    msg "git checkout done or server timeout"

    rm -rf ${srcdir}/${_gitname}-build
    git clone ${srcdir}/${_gitname} ${srcdir}/${_gitname}-build
}

package() {
    cd ${srcdir}/${_gitname}-build
    ./install.sh --global --destdir "${pkgdir}"
}
