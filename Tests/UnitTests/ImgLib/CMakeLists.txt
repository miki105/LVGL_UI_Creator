cmake_minimum_required(VERSION 3.0.0)

file(GLOB_RECURSE ImgLib_UT_Src
    "*.h"
    "*.cpp"
)

set(CXX g++-8)
set(cc gcc-8)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENSIONS ON)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(../../../3rdParty/LVGL)
include_directories(../../../3rdParty/LVGL/lvgl)
include_directories(../../../3rdParty/freetype-2.10.1/include)
include_directories(../../../3rdParty/spdlog-1.x/include)
include_directories(../../../LVSerial)
include_directories(../../../ImgLib)
include_directories(../../../3rdParty/Catch2/include)
include_directories(../../../3rdParty/libimagequant)
add_executable(ImgLibUnitTests ${ImgLib_UT_Src})
target_link_libraries(ImgLibUnitTests ImgLib)
target_link_libraries(ImgLibUnitTests imagequant)
