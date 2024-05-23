cmake_minimum_required(VERSION 3.22)
project(bytetrack)
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(include)
file(GLOB SRC ${PROJECT_SOURCE_DIR}/src/*.cpp)
add_library(bytetrack SHARED ${SRC})
target_link_libraries(bytetrack ${Opencv_LIBS})
install(DIRECTORY include/ DESTINATION include)
install(TARGETS bytetrack
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib
        RUNTIME DESTINATION bin
        INCLUDES DESTINATION include
)