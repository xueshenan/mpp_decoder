# vim: syntax=cmake

# ----------------------------------------------------------------------------
# add mpp basic components
# ----------------------------------------------------------------------------

add_library(mpp_base STATIC
    mpp_trie.cpp)


target_include_directories(mpp_base PRIVATE ${CMAKE_SOURCE_DIR}/base/inc)

target_link_libraries(mpp_base osal)

