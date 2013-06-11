# Maintainer: Jason Axelson <jason.axelsonATgmail.com>
# Contributor: Sean Escriva <sean.escrivaATgmail.com>
# Contributor: William Ting <william.h.tingATgmail.com>

# vim:set ts=4 sw=4 et:

pkgname=autojump-git
pkgver=release.v21.6.9.9.gd692bc6
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
source=('git+https://github.com/joelthelion/autojump.git')
md5sums=('SKIP')
install='install'

_gitname="autojump"

package() {
    cd ${_gitname}
    ./install.sh -Z /usr/share/zsh/site-functions/ --global --destdir "${pkgdir}"
}

pkgver() {
    cd ${_gitname}
    git describe --always | sed 's|-|.|g'
}
