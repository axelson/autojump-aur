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

_gitname="autojump"

package() {
    cd ${_gitname}
    ./install.sh -Z /usr/share/zsh/site-functions/ --global --destdir "${pkgdir}"
}

pkgver() {
    cd ${_gitname}
    git describe --always | sed 's|-|.|g'
}

#Please add the line to ~/.bashrc :
#
#[[ -s /home/jason/dev/autojump-aur/autojump-aur/pkg/autojump-git/etc/profile.d/autojump.bash ]] && . /home/jason/dev/autojump-aur/autojump-aur/pkg/autojump-git/etc/profile.d/autojump.bash
#
#You need to run 'source ~/.bashrc' before you can start using autojump. To remove autojump, run './uninstall.sh'
