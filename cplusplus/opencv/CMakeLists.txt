cmake_minimum_required(VERSION 3.24)
project(opencv)

set(CMAKE_CXX_STANDARD 17)

# set opencv
get_filename_component(ABSOLUTE_OpenCV_DIR ../../3rdparty/opencv/4.4.0 ABSOLUTE)
set(OpenCV_DIR ${ABSOLUTE_OpenCV_DIR}/lib/cmake/opencv4)
find_package(OpenCV REQUIRED)

MESSAGE("OpenCV version: ${OpenCV_VERSION}")
MESSAGE("OpenCV OpenCV_INCLUDE_DIRS: ${OpenCV_INCLUDE_DIRS}")
MESSAGE("OpenCV OpenCV_LIBS: ${OpenCV_LIBS}")

add_executable(opencv main.cpp)
target_link_libraries(opencv ${OpenCV_LIBS})

add_executable(RotateRectCrop rotate_rect_crop.cpp)
target_link_libraries(RotateRectCrop ${OpenCV_LIBS})

add_executable(Jpeg2Mat jpeg2mat.cpp)
target_link_libraries(Jpeg2Mat ${OpenCV_LIBS})

add_executable(ObjectDetect object_detect.cpp)
target_link_libraries(ObjectDetect ${OpenCV_LIBS})