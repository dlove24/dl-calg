# Copyright ( c ) 2012 David Love
#
# Permission is hereby granted, free of charge, to any person obtaining
# a copy of this software and associated documentation files ( the
# "Software" ), to deal in the Software without restriction, including
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
project ( calg_test )

# Set-up CMake
cmake_minimum_required ( VERSION 2.6 )

# Enable CTest
enable_testing()

#
# Test C-Algorithms Library: test-calg
#

# Add the global configure file to the search path
include_directories( ${CMAKE_CURRENT_SOURCE_DIR}/../../config )

# Add the C Algorithm headers to the search path
include_directories( ${CMAKE_CURRENT_SOURCE_DIR}/../include )

# Create a library for the C Algorithm data structures, used in the C primitives
add_library( test-calg STATIC
	../src/arraylist.c
	../src/avl-tree.c
	../src/root-tree.c
	../src/binary-heap.c
	../src/binomial-heap.c
	../src/bloom-filter.c
	../src/compare-int.c
	../src/compare-pointer.c
	../src/compare-string.c
	../src/hash-int.c
	../src/hash-pointer.c
	../src/hash-string.c
	../src/hash-table.c
	../src/list.c
	../src/queue.c
	../src/rb-tree.c
	../src/set.c
	../src/slist.c
	../src/trie.c
	)

# Create a library for the test framework
add_library (test-framework STATIC
	alloc-testing.c
	framework.c
	)

##
## Framework Tests
## 

add_executable ( ca-alloctest test-alloc-testing.c ) 
target_link_libraries( ca-alloctest test-calg test-framework)
add_test ( AllocTesting ca-alloctest)

##
## Data Structure Tests
##

add_executable ( ca-arraylist test-arraylist.c ) 
target_link_libraries( ca-arraylist test-calg test-framework)
add_test ( ArrayList ca-arraylist)

add_executable ( ca-avltree test-avl-tree.c ) 
target_link_libraries( ca-avltree test-calg test-framework)
add_test ( AvlTree ca-avltree)

add_executable ( ca-binaryheap test-binary-heap.c ) 
target_link_libraries( ca-binaryheap test-calg test-framework)
add_test ( BinaryHeap ca-binaryheap)

add_executable ( ca-binomialheap test-binomial-heap.c ) 
target_link_libraries( ca-binomialheap test-calg test-framework)
add_test ( BinomialHeap ca-binomialheap)

add_executable ( ca-bloomfilter test-bloom-filter.c ) 
target_link_libraries( ca-bloomfilter test-calg test-framework)
add_test ( BloomFilter ca-bloomfilter)

add_executable ( ca-hashtable test-hash-table.c ) 
target_link_libraries( ca-hashtable test-calg test-framework)
add_test ( HashTable ca-hashtable )

add_executable ( ca-list test-list.c ) 
target_link_libraries( ca-list test-calg test-framework)
add_test ( List ca-list)

add_executable ( ca-rbtree test-rb-tree ) 
target_link_libraries( ca-rbtree test-calg test-framework)
add_test ( RBTree ca-rbtree)

add_executable ( ca-set test-set.c ) 
target_link_libraries( ca-set test-calg test-framework)
add_test ( Set ca-set )

add_executable ( ca-slist test-slist.c ) 
target_link_libraries( ca-slist test-calg test-framework)
add_test ( SList ca-slist)

add_executable ( ca-trie test-trie.c ) 
target_link_libraries( ca-trie test-calg test-framework)
add_test ( Trie ca-trie )

add_executable ( ca-queue test-queue.c ) 
target_link_libraries( ca-queue test-calg test-framework)
add_test ( Queue ca-queue)

##
## Data Structure Helper Tests
##

add_executable ( ca-compare-functions test-compare-functions.c ) 
target_link_libraries( ca-compare-functions test-calg test-framework)
add_test ( CompareFunctions ca-compare-functions)

add_executable ( ca-hash-functions test-hash-functions.c ) 
target_link_libraries( ca-hash-functions test-calg test-framework)
add_test ( HashFunctions ca-hash-functions)


