# Maintainer: Tom Wizetek <tom@wizetek.com>
pkgname=vncviewer-enterprise
pkgver=4.6.3
pkgrel=1
pkgdesc="RealVNC Viewer Enterprise Edition"
url="http://www.realvnc.com/"
license=('custom')
arch=('i686' 'x86_64')
depends=('libxext')

[[ "${CARCH}" = "i686" ]] && _pkgbin="vnc-E4_6_3-x86_linux_viewer" && source=("${_pkgbin}.gz::http://www.realvnc.com/download/binary/548") && md5sums=('0e50a5441a25d6990fa5b076b7a76317')
[[ "${CARCH}" = "x86_64" ]] && _pkgbin="vnc-E4_6_3-x64_linux_viewer" && source=("${_pkgbin}.gz::http://www.realvnc.com/download/binary/510") && md5sums=('3af032c41dc25016a192c90603358383')

package() {
  install -D -m 755 ${srcdir}/${_pkgbin} ${pkgdir}/usr/bin/${_pkgbin}

  cat > ${pkgname}.desktop << EoF
[Desktop Entry]
Type=Application
Categories=Application;Network;
Terminal=false
Exec=/usr/bin/${_pkgbin}
Name=VNC Viewer Enterprise Edition for X
GenericName=Remote desktop client
Comment=Connect to VNC servers
EoF

  install -D -m 644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
}
