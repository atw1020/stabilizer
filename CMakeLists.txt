cmake_minimum_required(VERSION 3.19)
project(stabilizer)

# find the LLVM package
# you may need to specify the directory where llvm is installed by setting the LLVM_DIR environment variable
# here is an example for a homebrew install of llvm 12.0.0
# set(LLVM_DIR /opt/homebrew/Cellar/llvm/12.0.0_1/lib/cmake/llvm)
find_package(LLVM REQUIRED CONFIG)
include_directories(${LLVM_INCLUDE_DIR})
# include_directories("/opt/homebrew/opt/llvm/include")

set(CMAKE_CXX_STANDARD 17)
# TODO: find a better workaround
set(CMAKE_CXX_FLAGS -DLLVM_DISABLE_ABI_BREAKING_CHECKS_ENFORCING=1)

