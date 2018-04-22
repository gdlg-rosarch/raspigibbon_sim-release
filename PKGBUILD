# Script generated with Bloom
pkgdesc="ROS - The raspigibbon_control package"
url='http://github.com/rt-net/RaspberryPiGibbon/wiki'

pkgname='ros-kinetic-raspigibbon-control'
pkgver='0.0.1_1'
pkgrel=1
arch=('any')
license=('MIT'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-control-msgs'
'ros-kinetic-controller-interface'
'ros-kinetic-controller-manager'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-state-controller'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

depends=('ros-kinetic-control-msgs'
'ros-kinetic-controller-interface'
'ros-kinetic-controller-manager'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-state-controller'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=raspigibbon_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/raspigibbon_control $srcdir/raspigibbon_control
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

