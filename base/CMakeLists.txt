# vim: syntax=cmake

# ----------------------------------------------------------------------------
# add mpp basic components
# ----------------------------------------------------------------------------
add_library(mpp_base STATIC
    mpp_trie.cpp
    )

set_target_properties(mpp_base PROPERTIES FOLDER "base")

target_include_directories(mpp_base PRIVATE ${CMAKE_SOURCE_DIR}/base/inc)

target_link_libraries(mpp_base osal)

