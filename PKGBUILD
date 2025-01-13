pkgname=gitconf-git
_pkgname=${pkgname%-git}
pkgver=r1.3be1817
pkgrel=1
pkgdesc="git wrapper to version system configuration and dotfiles"
url="https://github.com/GenericMale/gitconf"
source=("git+https://github.com/GenericMale/gitconf")
arch=('any')
license=('EUPL-1.2')
depends=(
  'bash'
  'git'
  'acl'
)
optdepends=(
  'pacman: find untracked config files'
  'sudo: restore files outside users home'
)
sha256sums=("SKIP")

package() {
  cd "$srcdir/$_pkgname"
  install -Dm755 gitconf "$pkgdir/usr/bin/gitconf"
  install -Dm644 completions/fish "$pkgdir/usr/share/fish/vendor_completions.d/gitconf.fish"
}

pkgver() {
  cd "$srcdir/$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}
