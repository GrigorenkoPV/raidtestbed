project(testbed)
cmake_minimum_required(VERSION 2.9)
 set( CMAKE_CXX_FLAGS  "-mavx -O3 -finline      ")
add_subdirectory(RAID)
add_subdirectory(src)
add_subdirectory(confuse)
INCLUDE_DIRECTORIES(
  ./Include
  ./confuse
)




add_executable(testbed 
disk/RAIDProcessor.cpp disk/disk.cpp disk/array.cpp RAID/arithmetic.cpp
RAID/RS.cpp RAID/RAID5.cpp src/misc.cpp src/main.cpp src/usecase.cpp src/locker.cpp
confuse/confuse.c  confuse/lexer.c              
)
