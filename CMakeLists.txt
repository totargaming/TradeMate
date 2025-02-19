cmake_minimum_required(VERSION 3.10)

project(TradeMate)

# Add vcpkg toolchain file
set(CMAKE_TOOLCHAIN_FILE "/home/elvistran/Workspaces/vcpkg/scripts/buildsystems/vcpkg.cmake" CACHE STRING "Vcpkg toolchain file")

# Set the CMAKE_PREFIX_PATH
set(CMAKE_PREFIX_PATH "/home/elvistran/Workspaces/vcpkg/installed/x64-linux")

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find packages
find_package(fmt CONFIG REQUIRED)
find_package(jsoncpp CONFIG REQUIRED)
find_package(CURL CONFIG REQUIRED)

# Add executable
add_executable(TradeMate main.cpp GetSetClearTA.cpp TechnicalAnalysis.cpp IEX.cpp JSONdata.cpp)

# Link libraries
target_link_libraries(TradeMate PRIVATE CURL::libcurl JsonCpp::JsonCpp )