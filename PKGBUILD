# Maintainer: Zhengyu Xu <xzy3186[at]gmail[dot]com>
# Branch menu add the support of RB2.99
branch=master

pkgname=rhythmbox-plugin-coverart-browser-git
_gitname="coverart-browser"
pkgver=v0.9.354.gceea5d0
pkgrel=1
pkgdesc="a Rhythmbox plugin that lets you browse and play your music via an album art view"
url="https://github.com/fossfreedom/coverart-browser"
arch=('x86_64' 'i686')
license=('GPLv3')
depends=('glib2' 'gtk3' 'rhythmbox' 'python-mako' 'python-lxml' 'python-cairo'
'python-chardet' 'gst-plugins-ugly' 'gst-plugins-good' 'gst-plugins-bad'
'rhythmbox-plugin-coverart-search-providers')
conflicts=('rhythmbox-plugin-coverart-browser')
makedepends=('git')
source=("git://github.com/fossfreedom/coverart-browser.git#branch=$branch")
md5sums=('SKIP')
install=$pkgname.install

pkgver() {
  cd "$srcdir/$_gitname"
  git describe --always | sed 's|-|.|g'
}

package() {
  cd "${srcdir}/$_gitname"
  ############# fix crash bugs ################
  #sed -i "s/self.entry_changed_id/#self.entry_changed_id/g" coverart_album.py
  #sed -i "s/self._entry_changed/#self._entry_changed/g" coverart_album.py

  make DESTDIR=${pkgdir} install
}

# vim:set ts=2 sw=2 et:
