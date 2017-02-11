cmake_minimum_required(VERSION 3.6)
project(glad)

####################################
#         Compiler Options         #
####################################
set(CMAKE_C_STANDARD  11)
set(CMAKE_CXX_STANDARD 11)

set(C_WARNING_FLAGS "")
set(CXX_WARNING_FLAGS "")

set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static")
set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static-libstdc++ -static")

set(CMAKE_C_FLAGS)
set(CMAKE_C_FLAGS_DEBUG "-g")
set(CMAKE_C_FLAGS_MINSIZEREL "-Os -DNDEBUG")
set(CMAKE_C_FLAGS_RELEASE "-O3 -DNDEBUG")
set(CMAKE_C_FLAGS_RELWITHDBINFO "-O2 -g -DNDEBUG")

set(CMAKE_CXX_FLAGS)
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_MINSIZEREL "-Os -DNDEBUG")
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -DNDEBUG")
set(CMAKE_CXX_FLAGS_RELWITHDBINFO "-O2 -g -DNDEBUG")

####################################
#            Directories           #
####################################

include_directories(${PROJECT_SOURCE_DIR}/include)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/build/${CMAKE_BUILD_TYPE}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/build/${CMAKE_BUILD_TYPE}/lib)

set(SOURCE_FILES
        ${PROJECT_SOURCE_DIR}/include/glad/glad.h
        ${PROJECT_SOURCE_DIR}/include/KHR/khrplatform.h
        ${PROJECT_SOURCE_DIR}/src/glad.c)

add_library(glad STATIC ${SOURCE_FILES})
