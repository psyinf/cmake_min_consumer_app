cmake_minimum_required(VERSION 3.23)
project(minConsumingApp CXX)
include(FetchContent)
include(cmake/common.cmake)

FetchContent_Declare(
  minConsumerLib
  GIT_REPOSITORY https://github.com/psyinf/cmake_min_consumer_lib.git
  GIT_TAG        HEAD
  
  #SYSTEM
)
FetchContent_MakeAvailable(minConsumerLib)

add_executable(${PROJECT_NAME})

target_link_libraries(${PROJECT_NAME}
    PUBLIC
        minConsumerLib::minConsumerLib
)

target_sources(${PROJECT_NAME} 
    PRIVATE
        app/main.cpp 
)
