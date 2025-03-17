# Maintainer: tomatoes <tomatoes@tin-can.mozmail.com> 
_pkgbase=greybird-platinum 
_pkgbv=3.23.3
pkgname=$_pkgbase-git
pkgver=3.23.3.r0.0
pkgrel=2
pkgdesc="Greybird with a retro Platinum twist"
arch=('any')
url="https://github.com/ClassicOS-Themes/Greybird-Platinum"
license=('CC-BY-SA-3.0' 'GPL')
makedepends=('librsvg' 'meson' 'sassc')
optdepends=('gtk3: required for CSS/GTK3 theme'
            'lightdm-gtk-greeter: required for the LightDM GTK theme'
            'gtk-engine-murrine: GTK2 theme support'
            'lib32-gtk-engine-murrine: required for multilib')
source=("Greybird-Platinum::git+https://github.com/ClassicOS-Themes/Greybird-Platinum.git")
md5sums=('SKIP')

pkgver() {
  cd "Greybird-Platinum"
  printf "$_pkgbv.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  meson setup \
	  --prefix        /usr \
	  --libexecdir    lib \
	  --sbindir       bin \
	  --buildtype     plain \
	  --auto-features enabled \
	  "Greybird-Platinum" build
  meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"
}
