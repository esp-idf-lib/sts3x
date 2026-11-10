list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_LIST_DIR}/eil-cmake-utils/cmake)
include(eil_check_idf_features)
eil_check_idf_has_esp_drivers()

set(req i2cdev log esp_idf_lib_helpers esp_timer)

idf_component_register(
    SRCS sts3x.c
    INCLUDE_DIRS .
    REQUIRES ${req} 
)

include(eil_ci)
