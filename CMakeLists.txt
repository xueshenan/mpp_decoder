cmake_minimum_required(VERSION 3.14)

project(mpp_decoder)

set(MPP_DECODER_SRC
	mpi_dec_test.c
	utils/mpi_dec_utils.c
	utils/utils.c
	utils/mpp_opt.c)

add_subdirectory(osal)

add_subdirectory(base)

add_executable(${PROJECT_NAME}
	${MPP_DECODER_SRC})

target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/osal/inc
	${CMAKE_SOURCE_DIR}/base/inc)

find_package(PkgConfig REQUIRED)

pkg_check_modules(ROCKCHIP_MPP rockchip_mpp REQUIRED IMPORTED_TARGET)

target_link_libraries(${PROJECT_NAME} PRIVATE 
	PkgConfig::ROCKCHIP_MPP
	osal)
