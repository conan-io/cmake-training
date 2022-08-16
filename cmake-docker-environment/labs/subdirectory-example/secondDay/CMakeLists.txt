add_library(secondDay secondDay.cpp)
target_include_directories(secondDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)
target_link_libraries(secondDay PUBLIC firstDay)
