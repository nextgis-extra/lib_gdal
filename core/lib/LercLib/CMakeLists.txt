################################################################################
# Project:  CMake4GDAL
# Purpose:  CMake build scripts
# Author:   Dmitry Baryshnikov, dmitry.baryshnikov@nextgis.com
################################################################################
# Copyright (C) 2018, NextGIS <info@nextgis.com>
# Copyright (C) 2016 Mikhail Gusev
#
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the "Software"),
# to deal in the Software without restriction, including without limitation
# the rights to use, copy, modify, merge, publish, distribute, sublicense,
# and/or sell copies of the Software, and to permit persons to whom the
# Software is furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included
# in all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
# OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
# THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
# FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
# DEALINGS IN THE SOFTWARE.
################################################################################

if(WITH_LERC)

set(TARGET_NAME liblerc)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set(LIB_HHEADERS_PRIV
    BitMask.h
    BitStuffer2.h
    Defines.h
    Huffman.h
    Lerc_c_api.h
    Lerc_types.h
    Lerc.h
    Lerc2.h
    RLE.h
)

set(LIB_CSOURCES
    BitMask.cpp
	BitStuffer2.cpp
	Huffman.cpp
	Lerc2.cpp
	Lerc_c_api_impl.cpp
	Lerc.cpp
	RLE.cpp
)

add_library(${TARGET_NAME} OBJECT ${LIB_HHEADERS_PRIV} ${LIB_CSOURCES})
set(TARGET_OBJECTS ${TARGET_OBJECTS} $<TARGET_OBJECTS:${TARGET_NAME}> PARENT_SCOPE)

endif()
