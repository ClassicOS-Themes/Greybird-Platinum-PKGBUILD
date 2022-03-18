pkgname=greybird-platinum-git
pkgver=3.22.13+20
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
#  echo $(git describe --always --abbrev=0).r$(git rev-list --count master) | sed 's|-|.|g' | sed 's|v||g'
	echo "$(git describe --long | sed -r 's/-([0-9,a-g,A-G]{7}.*)//' | sed 's/-/+/' | sed 's/v//g' )"
}

build() {
  arch-meson "Greybird-Platinum" build
  meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"

}
