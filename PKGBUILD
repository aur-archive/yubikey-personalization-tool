# Maintainer: Christian Hesse <mail@eworm.de>
# Maintainer: Jimmy Xu <me@jimmyxu.org>

pkgname=yubikey-personalization-tool
pkgver=3.0.2
pkgrel=4
pkgdesc="Yubico Key Personalization Tool (GUI)"
arch=('i686' 'x86_64')
conflicts=('yubikey-personalization-gui')
replaces=('yubikey-personalization-gui')
url="https://www.yubico.com/personalization-tool"
license=('unknown')
source=("${pkgname}-${pkgver}.tar.gz::http://wiki.yubico.com/files/YubiKey%20Personalization%20Tool%20${pkgver}%20Installer-lin.tgz"
	"${pkgname}-${pkgver}-user-guide.pdf::http://static.yubico.com/var/uploads/pdfs/Cross_Platform_YubiKey_Personalization_Tool_3.0.1_User_guide_v5.pdf"
	'yubikey-personalization-tool.desktop'
	'ykpersonalization.png')
if [ "${CARCH}" = "x86_64" ]; then
   depends=('lib32-libusb' 'lib32-qt4')
fi
if [ "${CARCH}" = "i686" ]; then
   depends=('libusb' 'qt4')
fi

package() {
	install -D -m755 ${srcdir}/Yubico/YKPersonalization ${pkgdir}/usr/bin/YKPersonalization
	install -D -m644 ${srcdir}/${pkgname}-${pkgver}-user-guide.pdf ${pkgdir}/usr/share/doc/${pkgname}/user-guide.pdf
	install -D -m644 ${srcdir}/yubikey-personalization-tool.desktop ${pkgdir}/usr/share/applications/yubikey-personalization-tool.desktop
	install -D -m644 ${srcdir}/ykpersonalization.png ${pkgdir}/usr/share/pixmaps/ykpersonalization.png
}

sha256sums=('e1ad18fee353c66470bc23b2ae49b81d06ebf1aabe4c56cfa9a7d8cee7359150'
            'e987fc3fd709b72584f77e1a743f70054e514136ceae2eac9f8074e1b6916bd3'
            'f1ccfad8f5728fbbc54aca35ae2642100cc47b8037e8bf127c1f73a8123eaad0'
            '8c7a7f6116ddb75825d7f27f58cdcd6df3cfbb12d73b079c358ceb532fdd7ad6')
