# Maintainer: Anatol Pomozov <anatol.pomozov@gmail.com>

_gemname=rake
pkgname=ruby-$_gemname
pkgver=12.3.0
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
sha1sums=('8f9e0c0a5fc64bb5d5d4343224ea11497fc1e653')

package() {
  local _gemdir="$(ruby -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install --no-document -i "$pkgdir/$_gemdir" -n "$pkgdir/usr/bin" $_gemname-$pkgver.gem
  rm "$pkgdir/$_gemdir/cache/$_gemname-$pkgver.gem"
}
