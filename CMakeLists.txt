cmake_minimum_required(VERSION 2.8)

project(helala_stereo)

set("OpenCV_DIR" "/Users/faisal/Code/opencv3/share/OpenCV")
find_package(OpenCV REQUIRED)

MESSAGE(STATUS "Include dirs ${OpenCV_INCLUDE_DIRS}")
MESSAGE(STATUS "LINK LIBRARIES ${OpenCV_LIBS}")

set(SOURCES
    guidedfilter.cpp
    main.cpp
    SLIC.cpp
    util.cpp
    volanalysis.cpp
    writeMat.cpp
)

set(HEADERS
    guidedfilter.h
    kdtree.h
    main.h
    params.h
    PM.h
    pm1.h
    SLIC.h
    util.h
    volanalysis.h
    writeMat.h
)

add_executable(helala_stereo ${SOURCES})

include_directories(/Users/faisal/Code/opencv3/include)
include_directories(/Users/faisal/Code/opencv3/include/opencv)

add_definitions( "-Wc++11-compat-deprecated-writable-strings" "-std=c++11" )

target_link_libraries(helala_stereo ${OpenCV_LIBS})
