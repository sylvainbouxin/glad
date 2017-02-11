cmake_minimum_required(VERSION 3.6)
project(glad)

####################################
#            Directories           #
####################################

include_directories(${PROJECT_SOURCE_DIR}/include)

set(SOURCE_FILES
        ${PROJECT_SOURCE_DIR}/include/glad/glad.h
        ${PROJECT_SOURCE_DIR}/include/KHR/khrplatform.h
        ${PROJECT_SOURCE_DIR}/src/glad.c)

add_library(glad SHARED ${SOURCE_FILES})
