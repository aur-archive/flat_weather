# Contributer: giacomogiorgianni@gmail.com 

pkgname=flat_weather
pkgver=1.9.0
pkgrel=3
pkgdesc="weather for conky"
arch=('any')
url="http://pabloferz.deviantart.com/art/Flat-Weather-for-Conky-208130863"
license=('GPL')
categories=()
depends=('conky-lua' 'bash' 'sh')
makedepends=(p7zip)
options=(!emptydirs)
source=("http://fc04.deviantart.net/fs71/f/2012/332/6/8/flat_weather_for_conky_by_pabloferz-d3fwysv.zip" "conky-start" "flat_weather.desktop")
md5sums=('e87f218e9e84a54f01578c13f3186df3
	  f18f863c48b5f41c0f65800919ca51f4
	  04468a41b7067157929b0717f4279479')

build() {
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/usr/share/autostart
  install -m 0755 $startdir/conky-start $pkgdir/usr/bin/ || return 1
  install -m 0644 $startdir/$pkgname.desktop $pkgdir/usr/share/autostart/$pkgname.desktop || return 1
  
  install -m 0775 -do $LOGNAME $pkgdir/$HOME/.conky
  7z x Flat-Weather.iso
  cp -pR $srcdir/Flat-Weather $pkgdir/$HOME/.conky
  chown -R $LOGNAME:users $pkgdir/$HOME/.conky/
  echo "ATTENZION!!!!!! To cange City Name and LOCID(.conky/Flat-Weather/conkyrc)---> http://aspnetresources.com/tools/weatherIdResolver"
}
