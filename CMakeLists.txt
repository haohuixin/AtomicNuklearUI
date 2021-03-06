#
# Copyright (c) 2016 Rokas Kupstys.
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
# THE SOFTWARE.
#
add_library(AtomicNuklearUI STATIC AtomicNuklearUI.h AtomicNuklearUI.cpp nuklear/nuklear.h)
target_compile_definitions(AtomicNuklearUI
    PUBLIC
    -DNK_INCLUDE_VERTEX_BUFFER_OUTPUT=1
    -DNK_INCLUDE_FONT_BAKING=1
    -DNK_INCLUDE_DEFAULT_FONT=1
    -DNK_INCLUDE_COMMAND_USERDATA=1
    -DNK_INCLUDE_STANDARD_IO=1
    -DNK_INCLUDE_FIXED_TYPES=1
    -DNK_INCLUDE_DEFAULT_ALLOCATOR=1
    -DNK_INCLUDE_STANDARD_VARARGS=1
)
target_link_libraries(AtomicNuklearUI Atomic)
target_include_directories(AtomicNuklearUI PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
if (NOT MSVC)
    target_compile_options(AtomicNuklearUI PUBLIC -std=c++11)
endif ()
