# Maintainer: Edoardo Maria Elidoro <edoardo.elidoro@gmail.com>
# Contributor: Jib <jbc.as (AT) free.fr>

pkgname=gtk-theme-ellanna
_pkgname="Ellanna theme"
pkgver=1.5.1
pkgrel=2
pkgdesc="Ellanna theme for Xfce and Mate."
arch=(any)
depends=('gtk-engine-murrine>=0.98')
optdepends=('slim-theme-ellanna: matching theme for slim login manager')
license=('GPL')
source=(https://launchpad.net/~bisigi/+archive/ppa/+files/ellanna-theme_1.5.1.maverick.ppa2.tar.gz
        ellanna.patch)
url="http://www.bisigi-project.org"
md5sums=('3b1e14ef420494ed6409b8630c530bb2'
         '43322d5267b314790cb3ab00976516ed')

package() {
   cd ${srcdir}/"$_pkgname"
   # install dirs
   install -d ${pkgdir}/usr/share/{themes,icons,pixmaps/backgrounds/gnome/nature,gnome-background-properties,doc/bisigi/ellanna}
   tar -xzf Gtk/ellanna.tar.gz -C Gtk/
   echo "Unpacking icons..."
   tar -xjf Icons/ellanna.tar.bz2 -C Icons/
   patch -Np0 <${srcdir}/ellanna.patch
   cp -R Gtk/ellanna/ ${pkgdir}/usr/share/themes/
   cp -R Icons/ellanna/ ${pkgdir}/usr/share/icons
   install -D -m644 Wallpaper/ellanna.jpg ${pkgdir}/usr/share/pixmaps/backgrounds/gnome/nature	
   install -D -m644 Wallpaper/ellanna-wallpaper.xml ${pkgdir}/usr/share/gnome-background-properties
   install -D -m644 credits.txt ${pkgdir}/usr/share/doc/bisigi/ellanna/
}
