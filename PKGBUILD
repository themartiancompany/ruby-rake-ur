# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2024, 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer:
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
# Maintainer:
#   Anatol Pomozov
#     <anatol.pomozov@gmail.com>

_gemname=rake
_pkg="${_gemname}"
pkgname="ruby-${_pkg}"
pkgver=13.2.1
pkgrel=4
_pkgdesc=(
  'Make-like build tool'
  'implemented in Ruby.'
)
provides=(
  "rake=${pkgver}"
)
arch=(
  'any'
)
url="https://ruby.github.io/${_pkg}/"
license=(
  'MIT'
)
depends=(
  "ruby"
)
options=(
  "!emptydirs"
)
_tarname="${_pkg}-${pkgver}"
source=(
  "https://rubygems.org/downloads/${_tarname}.gem"
)
noextract=(
  "${_pkg}-${pkgver}.gem"
)
sha512sums=(
  '1671f477527347084046001fee8bc4b49b990079de1acf876bf588c2d9cdc2aba302e95a1e9dfb7300283f0268799a4b3b8bca8f962cb7e09a255e9288f83f37'
)
b2sums=(
  '597b1a57583adaca0b3cde98f37a23856c54ab7a350f668abe4d67d38c855322ef613170fdf1e75907743ad534f61f8cd18641b4a97b8db77e675f4968ac07ee'
)

package() {
  local \
    _gemdir \
    _gem_install_opts=()
  _gemdir="$( \
    ruby \
      -e'puts Gem.default_dir')"
  if [[ "${_os}" == "GNU/Linux" ]]; then
    _gem_install_opts+=(
      --ignore-dependencies
    )
  fi
  _gem_install_opts+=(
    --no-user-install
    --no-document
    -i
      "${pkgdir}/${_gemdir}"
    -n
      "${pkgdir}/usr/bin"
  )
  gem \
    "${_gem_install_opts[@]}" \
    "${_tarname}.gem"
  rm \
    "${pkgdir}/${_gemdir}/cache/${_tarname}.gem"
}
