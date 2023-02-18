pkgname=greybird-platinum-git
pkgver=3.23.3_platinum_git_d3dfb6c

pkgrel=1
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
	echo "3.23.3_platinum_git_$(git rev-parse --short HEAD)"
}

build() {
  arch-meson "Greybird-Platinum" build
  meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"

}
