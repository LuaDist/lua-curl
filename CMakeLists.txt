# Copyright (C) 2011 LuaDist.
# Created by David Manura
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( Lua-cURL C )
cmake_minimum_required ( VERSION 2.6 )
include ( dist.cmake )

# Find curl
find_package ( CURL REQUIRED )
include_directories ( ${CURL_INCLUDE_DIR} )

install_lua_module ( cURL
  src/Lua-cURL.c
  src/Lua-utility.c
  src/Lua-cURL-getinfo.c
  src/Lua-cURL-setopt.c
  src/Lua-cURL-callback.c
  src/Lua-cURL-post.c
  src/Lua-cURL-multi.c
  src/Lua-cURL-share.c )
target_link_libraries ( cURL ${CURL_LIBRARY} )

install_data ( TODO COPYING )
install_doc ( doc/api.rst )
install_example ( examples )

# missing tests
