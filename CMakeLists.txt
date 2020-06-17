cmake_minimum_required (VERSION 3.0)
project (app VERSION 0.0.1)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

configure_file(src/Config.hpp.in Config.hpp)

add_executable (${PROJECT_NAME}
                src/main.cpp 
                )

target_include_directories(${PROJECT_NAME} PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )

install(TARGETS ${PROJECT_NAME} DESTINATION bin)
install(FILES "${PROJECT_BINARY_DIR}/Config.hpp"
        DESTINATION include
        )

include(InstallRequiredSystemLibraries)
set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_CURRENT_SOURCE_DIR}/LICENSE.md")
set(CPACK_PACKAGE_VERSION_MAJOR "${app_VERSION_MAJOR}")
set(CPACK_PACKAGE_VERSION_MINOR "${app_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${app_VERSION_PATCH}")
include(CPack)
