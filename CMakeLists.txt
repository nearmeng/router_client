cmake_minimum_required (VERSION 3.20)

project(router_client)
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

#set(CMAKE_VERBOSE_MAKEFILE on)

include (precompile)
include (project)
include (fetch_content)

fetch_content(common https://github.com/nearmeng/common.git master)
fetch_content(router_proto https://github.com/nearmeng/router_proto.git master)

init_project()

pre_project(router_client STATIC)

add_project()

post_project()


target_include_directories(${TARGET_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/inc)
target_link_libraries (${TARGET_NAME}
    mango::common
    mango::router_proto
)