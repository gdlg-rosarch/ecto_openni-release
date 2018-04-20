# Script generated with Bloom
pkgdesc="ROS - Ecto bindings for the openni sensor."
url='http://plasmodic.github.io/ecto_openni'

pkgname='ros-kinetic-ecto-openni'
pkgver='0.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'libusbx'
'openni'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-ecto'
)

depends=('boost'
'libusbx'
'openni'
'ros-kinetic-cv-bridge'
'ros-kinetic-ecto'
)

conflicts=()
replaces=()

_dir=ecto_openni
source=()
md5sums=()

prepare() {
    cp -R $startdir/ecto_openni $srcdir/ecto_openni
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

