# Maintainer: Jakob Gahde <j5lx@fmail.co.uk>

pkgname=ocaml-core
pkgver=0.11.3
pkgrel=1
epoch=1
pkgdesc="Industrial strength alternative to OCaml's standard library"
arch=('i686' 'x86_64')
url="https://github.com/janestreet/core"
license=('Apache')
depends=('ocaml' 'ocaml-base' 'ocaml-configurator' 'ocaml-core_kernel' 'ocaml-ppx_assert' 'ocaml-ppx_jane' 'ocaml-sexplib' 'ocaml-spawn' 'ocaml-stdio' 'ocaml-migrate-parsetree' 'ocaml-ppxlib')
optdepends=('ocaml-utop: for coretop support'
            'ocamlbuild: for corebuild support')
makedepends=('dune')
options=('!strip')
source=("https://github.com/janestreet/core/archive/v${pkgver}.tar.gz")
md5sums=('aa4e3acc952f1d5538a26f12e0b10fec')

build() {
  cd "${srcdir}/core-${pkgver}"

  jbuilder build
}

package() {
  cd "${srcdir}/core-${pkgver}"

  install -dm755 "${pkgdir}$(ocamlfind -printconf destdir)" "${pkgdir}/usr/share"
  jbuilder install --prefix "${pkgdir}/usr" --libdir "${pkgdir}$(ocamlfind -printconf destdir)"
  mv "${pkgdir}/usr/doc" "${pkgdir}/usr/share/"
}
