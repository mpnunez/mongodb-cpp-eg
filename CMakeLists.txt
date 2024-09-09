cmake_minimum_required(VERSION 3.10)
project(cmongodb)

set(CMAKE_CXX_STANDARD 14)

include_directories(/home/mpnunez/coding/facile-tutorials/cpp-installs/mongodb/vcpkg/installed/x64-linux/include)
link_directories(/home/mpnunez/coding/facile-tutorials/cpp-installs/mongodb/vcpkg/installed/x64-linux/lib)


find_package(libbsoncxx-static REQUIRED)
find_package(libmongocxx-static REQUIRED)

include_directories(${LIBMONGOCXX_STATIC_LIBRARIES})
include_directories(${LIBBSONCXX_STATIC_LIBRARIES})
include_directories(${LIBMONGOCXX_STATIC_INCLUDE_DIRS})
include_directories(${LIBBSONCXX_STATIC_INCLUDE_DIRS})

message(STATUS "${LIBMONGOCXX_STATIC_LIBRARIES}")
message(STATUS "${LIBMONGOCXX_STATIC_INCLUDE_DIRS}")

message(STATUS "${LIBBSONCXX_STATIC_LIBRARIES}")
message(STATUS "${LIBBSONCXX_STATIC_INCLUDE_DIRS}")

add_executable(cmongodb src/main.cpp)

target_link_libraries(cmongodb ${LIBMONGOCXX_STATIC_LIBRARIES} ${LIBBSONCXX_STATIC_LIBRARIES})
