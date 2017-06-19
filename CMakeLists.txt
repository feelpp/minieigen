###  CMakeLists.txt; coding: utf-8 --- 

#  Author(s): Christophe Prud'homme <christophe.prudhomme@feelpp.org>
#       Date: 18 Jun 2017
#
#  Copyright (C) 2017 Feel++ Consortium
#
# Distributed under the GPL(GNU Public License):
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.
#
#

#file(GLOB SRC src/miniEigen.cpp src/double-conversion/*.cc)
set(SRCS
  src/expose-boxes.cpp
  src/expose-complex.cpp
  src/expose-converters.cpp
  src/expose-matrices.cpp
  src/expose-quaternion.cpp
  src/expose-vectors.cpp
  src/minieigen.cpp
  src/double-conversion/bignum.cc
  src/double-conversion/bignum-dtoa.cc
  src/double-conversion/cached-powers.cc
  src/double-conversion/diy-fp.cc
  src/double-conversion/double-conversion.cc
  src/double-conversion/fast-dtoa.cc
  src/double-conversion/fixed-dtoa.cc
  src/double-conversion/strtod.cc)

include_directories( ${PYTHON_INCLUDE_DIRS} ${EIGEN3_INCLUDE_DIR} )
add_library( feelpp_minieigen SHARED ${SRCS} )
target_link_libraries( feelpp_minieigen ${Boost_PYTHON_LIBRARY} ) 
#g++ -ansi src/miniEigen.cpp src/double-conversion/*.cc -o minieigen.so -shared -fPIC `pkg-config python --cflags` -lboost_python -I/usr/include/eigen3
