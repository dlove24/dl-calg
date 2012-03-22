# Copyright (c) 2012 David Love
#
# Permission is hereby granted, free of charge, to any person obtaining
# a copy of this software and associated documentation files (the
# "Software"), to deal in the Software without restriction, including
# without limitation the rights to use, copy, modify, merge, publish,
# distribute, sublicense, and/or sell copies of the Software, and to
# permit persons to whom the Software is furnished to do so, subject to
# the following conditions:
#
# The above copyright notice and this permission notice shall be
# included in all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
# EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
# MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
# NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
# LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
# OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
# WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

##
## Project Definition
##

# Project Name
project ( libcalg )

##
## C Library Sources
##

#
# C-Algorithms Library: calg
#

# Add the C Algorithm headers to the search path
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# Create a library for the C Algorithm data structures, used in the C primitives
add_library( calg STATIC
	src/arraylist.c
	src/avl-tree.c
	src/binary-heap.c
	src/binomial-heap.c
	src/bloom-filter.c
	src/compare-int.c
	src/compare-pointer.c
	src/compare-string.c
	src/hash-int.c
	src/hash-pointer.c
	src/hash-string.c
	src/hash-table.c
	src/list.c
	src/queue.c
	src/rb-tree.c
	src/set.c
	src/slist.c
	src/trie.c
	)
