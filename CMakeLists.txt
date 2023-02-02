cmake_minimum_required(VERSION 3.12)

set(TINYXML_VERSION 1.0)
set(PROJECT_NAME tinyxml)
project(${PROJECT_NAME} VERSION ${TINYXML_VERSION} LANGUAGES C CXX)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wno-unknown-pragmas -Wno-format -O3")

set(TINYXML_SRS tinyxml.cpp tinystr.cpp tinyxmlerror.cpp tinyxmlparser.cpp)
set(TINYXML_HEADERS tinyxml.h tinystr.h)

# set library output path
# set(LIBRARY_OUTPUT_DIRECTORY lib)
# set(LIBRARY_OUTPUT_PATH lib)
add_library(${PROJECT_NAME}-${TINYXML_VERSION} SHARED ${TINYXML_SRS} ${TINYXML_HEADERS})
add_library(${PROJECT_NAME} STATIC ${TINYXML_SRS} ${TINYXML_HEADERS})
add_library(${PROJECT_NAME}::${PROJECT_NAME} ALIAS ${PROJECT_NAME})
