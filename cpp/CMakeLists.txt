cmake_minimum_required(VERSION 3.28 FATAL_ERROR)
project(examples)

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
    set(CMAKE_BUILD_TYPE Release CACHE STRING "Choose the type of build." FORCE)
    message(STATUS "Setting default build type to: ${CMAKE_BUILD_TYPE}")
endif()

list(APPEND CMAKE_PREFIX_PATH /home/kami/libs/cpp/libtorch/)
find_package(Torch REQUIRED)
find_package(xTorch REQUIRED)
find_package(LibLZMA REQUIRED)
find_package(LibArchive REQUIRED)
find_package(OpenSSL REQUIRED)
find_package(CURL REQUIRED)
find_package(OpenCV REQUIRED)
find_package(ZLIB REQUIRED)
find_package(SndFile REQUIRED)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

#set(TEST_SOURCE_FILES src/mnist.cpp)

#add_executable(${PROJECT_NAME} ${TEST_SOURCE_FILES})
#set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)

#include_directories(/usr/include)

#target_include_directories(${PROJECT_NAME} PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
#target_link_libraries(${PROJECT_NAME}
#        ${CURL_LIBRARIES}
#        ${TORCH_LIBRARIES}
#        ${OpenCV_LIBS}
#        ${ZLIB_LIBS}
#        ${ZIP_LIBRARIES}
#        zip
#        ${ZLIB_LIBRARIES}
#        ${LIBTAR_LIBRARY}
#        OpenSSL::SSL
#        #        OpenSSL::Crypto
#        LibLZMA::LibLZMA
#        ${LibArchive_LIBRARIES}
#        ${XTORCH_LIBRARIES}
#        xTorch::xTorch
#)

set(TEST_LIBRARIES ${CURL_LIBRARIES}
        ${TORCH_LIBRARIES}
        ${OpenCV_LIBS}
        ${ZLIB_LIBS}
        ${ZIP_LIBRARIES}
        zip
        ${ZLIB_LIBRARIES}
        ${LIBTAR_LIBRARY}
        OpenSSL::SSL
        OpenSSL::Crypto
        LibLZMA::LibLZMA
        ${LibArchive_LIBRARIES}
        ${XTORCH_LIBRARIES}
        xTorch::xTorch


)


#========================================================LENET5========================================================#

# ----------------------------lenet5-mnist ---------------------------- #
add_executable(lenet5-mnist src/lenet5/mnist.cpp)
target_link_libraries(lenet5-mnist "${TORCH_LIBRARIES}")
set_property(TARGET lenet5-mnist PROPERTY CXX_STANDARD 17)
target_include_directories(lenet5-mnist PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(lenet5-mnist ${TEST_LIBRARIES})



# ----------------------------lenet5-fashion-mnist ---------------------------- #
add_executable(lenet5-fashion-mnist src/lenet5/fashion_mnist.cpp)
target_link_libraries(lenet5-fashion-mnist "${TORCH_LIBRARIES}")
set_property(TARGET lenet5-fashion-mnist PROPERTY CXX_STANDARD 17)
target_include_directories(lenet5-fashion-mnist PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(lenet5-fashion-mnist ${TEST_LIBRARIES})

# ----------------------------lenet5-cifar10 ---------------------------- #
add_executable(lenet5-cifar10 src/lenet5/cifar10.cpp)
target_link_libraries(lenet5-cifar10 "${TORCH_LIBRARIES}")
set_property(TARGET lenet5-cifar10 PROPERTY CXX_STANDARD 17)
target_include_directories(lenet5-cifar10 PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(lenet5-cifar10 ${TEST_LIBRARIES})

# ----------------------------lenet5-cifar100 ---------------------------- #
add_executable(lenet5-cifar100 src/lenet5/cifar100.cpp)
target_link_libraries(lenet5-cifar100 "${TORCH_LIBRARIES}")
set_property(TARGET lenet5-cifar100 PROPERTY CXX_STANDARD 17)
target_include_directories(lenet5-cifar100 PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(lenet5-cifar100 ${TEST_LIBRARIES})

# ----------------------------lenet5-imagenette ---------------------------- #
add_executable(lenet5-imagenette src/lenet5/imagenette.cpp)
target_link_libraries(lenet5-imagenette "${TORCH_LIBRARIES}")
set_property(TARGET lenet5-imagenette PROPERTY CXX_STANDARD 17)
target_include_directories(lenet5-imagenette PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(lenet5-imagenette ${TEST_LIBRARIES})

# ----------------------------lenet5-food101 ---------------------------- #
add_executable(lenet5-food101 src/lenet5/food101.cpp)
target_link_libraries(lenet5-food101 "${TORCH_LIBRARIES}")
set_property(TARGET lenet5-food101 PROPERTY CXX_STANDARD 17)
target_include_directories(lenet5-food101 PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(lenet5-food101 ${TEST_LIBRARIES})




#========================================================ALEXNET=======================================================#

# ----------------------------lenet5-mnist ---------------------------- #
add_executable(alexnet-mnist src/alexnet/mnist.cpp)
target_link_libraries(alexnet-mnist "${TORCH_LIBRARIES}")
set_property(TARGET alexnet-mnist PROPERTY CXX_STANDARD 17)
target_include_directories(alexnet-mnist PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(alexnet-mnist ${TEST_LIBRARIES})



# ----------------------------lenet5-fashion-mnist ---------------------------- #
add_executable(alexnet-fashion-mnist src/alexnet/fashion_mnist.cpp)
target_link_libraries(alexnet-fashion-mnist "${TORCH_LIBRARIES}")
set_property(TARGET alexnet-fashion-mnist PROPERTY CXX_STANDARD 17)
target_include_directories(alexnet-fashion-mnist PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(alexnet-fashion-mnist ${TEST_LIBRARIES})

# ----------------------------lenet5-cifar10 ---------------------------- #
add_executable(alexnet-cifar10 src/alexnet/cifar10.cpp)
target_link_libraries(alexnet-cifar10 "${TORCH_LIBRARIES}")
set_property(TARGET alexnet-cifar10 PROPERTY CXX_STANDARD 17)
target_include_directories(alexnet-cifar10 PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(alexnet-cifar10 ${TEST_LIBRARIES})

# ----------------------------lenet5-cifar100 ---------------------------- #
add_executable(alexnet-cifar100 src/alexnet/cifar100.cpp)
target_link_libraries(alexnet-cifar100 "${TORCH_LIBRARIES}")
set_property(TARGET alexnet-cifar100 PROPERTY CXX_STANDARD 17)
target_include_directories(alexnet-cifar100 PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(alexnet-cifar100 ${TEST_LIBRARIES})

# ----------------------------lenet5-imagenette ---------------------------- #
add_executable(alexnet-imagenette src/alexnet/imagenette.cpp)
target_link_libraries(alexnet-imagenette "${TORCH_LIBRARIES}")
set_property(TARGET alexnet-imagenette PROPERTY CXX_STANDARD 17)
target_include_directories(alexnet-imagenette PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(alexnet-imagenette ${TEST_LIBRARIES})

# ----------------------------lenet5-food101 ---------------------------- #
add_executable(alexnet-food101 src/alexnet/food101.cpp)
target_link_libraries(alexnet-food101 "${TORCH_LIBRARIES}")
set_property(TARGET alexnet-food101 PROPERTY CXX_STANDARD 17)
target_include_directories(alexnet-food101 PRIVATE ${LIBTAR_INCLUDE_DIR} ${TORCH_INCLUDE_DIRS} ${LibArchive_INCLUDE_DIRS} ${XTORCH_INCLUDE_DIRS})
target_link_libraries(alexnet-food101 ${TEST_LIBRARIES})
