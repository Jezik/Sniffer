cmake_minimum_required(VERSION 3.10)
project(sniffer LANGUAGES CXX)

set(CMAKE_CXX_STANDART 17)
set(CMAKE_CXX_STANDART_REQUIRED ON)

find_package(PkgConfig REQUIRED)
pkg_check_modules(PCAP REQUIRED libpcap)

include_directories(${PCAP_INCLUDE_DIRS})
link_directories(${PCAP_LIBRARY_DIRS})

add_executable(sniffer src/main.cpp)

target_link_libraries(sniffer ${PCAP_LIBRARIES})
