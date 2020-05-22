cmake_minimum_required(VERSION 3.16)
project(dosdefender_ld31 C)

set(CMAKE_C_STANDARD 99)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra -Os -nostdlib -m32 -march=i386 \
  -Wno-unused-function \
  -ffreestanding -fomit-frame-pointer -fwrapv -fno-strict-aliasing \
  -fno-leading-underscore -fno-pic -fno-stack-protector \
  -Wl,--nmagic,-static,-T${CMAKE_SOURCE_DIR}/com.ld")

include_directories(.)

add_executable(dosdef.com dosdef.c)
