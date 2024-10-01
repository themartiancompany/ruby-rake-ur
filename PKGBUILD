# Maintainer: Anatol Pomozov <anatol.pomozov@gmail.com>

_gemname=rake
pkgname=ruby-$_gemname
pkgver=13.1.0
pkgrel=1
pkgdesc='Make-like build tool implemented in Ruby'
provides=(rake)
arch=(any)
url='https://ruby.github.io/rake/'
license=(MIT)
depends=(ruby)
options=(!emptydirs)
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)
sha512sums=('1883c00ebdc8471941a93472c4301c93d8c2204a95938b6b249e944888854c5a29b5a1a6a4390fed72cdb471ed65642ddc95f52adcd0d0efbce07cb0792d2e28')

package() {
  local _gemdir="$(ruby -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install --no-document -i "$pkgdir/$_gemdir" -n "$pkgdir/usr/bin" $_gemname-$pkgver.gem
  rm "$pkgdir/$_gemdir/cache/$_gemname-$pkgver.gem"
}
