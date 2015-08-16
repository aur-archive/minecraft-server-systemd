# Maintainer: Isaac C. Aronson <isaac at pingas dot org>

pkgname=minecraft-server-systemd
pkgver=1.4.7
pkgrel=1
epoch=
pkgdesc="Minecraft server unit files and script"
arch=(any)
url="http://minecraft.net/"
license=('custom')
depends=('java-runtime-headless' 'systemd' 'screen' 'expect')
conflicts=('minecraft-server' 'minecraft-canary')
options=(emptydirs)
install=minecraft-server.install
changelog=
source=(https://s3.amazonaws.com/MinecraftDownload/launcher/minecraft_server.jar
        minecraftd
        minecraftd.service)
noextract=('minecraft_server.jar')  
md5sums=('f69ac4bfce2dfbce03fe872518f75a05'
         '058eb25c49c5a8f2e3166f5046fd1fad'
         '98df0cca61c6833ad032559f07b4acb1')

package() {
  install -Dm755 "$srcdir/minecraftd" "$pkgdir/usr/bin/minecraftd"
  install -Dm644 "$srcdir/minecraft_server.jar" "$pkgdir/srv/minecraft/minecraft_server.jar"
  install -Dm644 "$srcdir/minecraftd.service" "$pkgdir/usr/lib/systemd/system/minecraftd.service"

  install -d "$pkgdir/srv/minecraft"
}
