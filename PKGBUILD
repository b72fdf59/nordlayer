# Maintainer: Deividas Gedgaudas <sidicer at gmail dot com>
# Contributor: Niklas Engvall <niklas at engvall dot it>

pkgname=nordlayer
pkgver=3.3.2
pkgrel=0
pkgdesc="Proprietary VPN client for linux"
arch=('i686' 'x86_64')
url="https://nordlayer.com"
license=('custom')
replaces=('nordvpnteams-bin')
conflicts=('nordvpnteams-bin')
depends=('bash')
#backup=('etc/default/nordlayer' 'etc/nordlayer/config.hcl' 'etc/nordlayer/ipsec.secrets')
options=('!strip' '!emptydirs')
install=${pkgname}.install
source_x86_64=("https://downloads.nordlayer.com/linux/latest/debian/pool/main/${pkgname}_${pkgver}_amd64.deb")
sha512sums_x86_64=('1d3bc4a30b717a92394c373c02adae5c724741682757e72694f6f35f514f46c7be66fbc5f679fdb74b87e4ed12bf47683603206bfc9a6526bd25fd111701f877 ')

package(){
	# Extract package data
	#tar xzf data.tar.gz -C "${pkgdir}"
	bsdtar -O -xf *.deb data.tar.gz | bsdtar -C "${pkgdir}" -xJf -
    cp -r "${pkgdir}/usr/sbin/." "${pkgdir}/usr/bin"
    sed -i 's+sbin+bin+g' "${pkgdir}/usr/lib/systemd/system/nordlayer.service"
    rm -r "${pkgdir}/usr/sbin"
}
