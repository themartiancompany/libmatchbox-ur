# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
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

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Truocolo <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer: Pellegrino Prevete (dvorak) <pellegrinoprevete@gmail.com>
# Maintainer: Pellegrino Prevete (dvorak) <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Henrique C. Alves <hcarvalhoalves@gmail.com>

_proj="yoctoproject"
_pkg="matchbox"
pkgname="lib${_pkg}"
pkgver=1.12
pkgrel=2
pkgdesc="Base library for Matchbox WM"
arch=(
  'x86_64'
  'arm'
  'aarch64'
  'pentium4'
  'i686'
  'armv7l'
  'mips'
)
license=(
  'LGPL'
)
depends=(
  'pango'
  'libpng'
  'libjpeg-turbo'
  'xsettings-client'
  'libxext'
)
_http="https://git.${_proj}.org"
_ns="${pkgname}"
url="https://www.${_proj}.org/software-item/${_pkg}"
source=(
  "${_http}/${_ns}/snapshot/${pkgname}-${pkgver}.tar.gz"
)
sha256sums=(
  '648d7e1af82e69b79c0932ff9f85e6781584eada5da8662f70196916dd208f55'
)

build() {
  cd \
    "${srcdir}/${pkgname}-${pkgver}"
  ./autogen.sh
  ./configure \
    --prefix=/usr \
    --enable-pango \
    --enable-jpeg \
    --enable-xsettings
  make
}

package() {
  cd \
    "${srcdir}/${pkgname}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}
