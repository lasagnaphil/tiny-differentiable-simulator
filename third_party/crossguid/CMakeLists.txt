
ADD_LIBRARY(crossguid guid.cpp)

if(WIN32)
	target_compile_definitions(crossguid PUBLIC GUID_WINDOWS PRIVATE GUID_WINDOWS)
else()
	target_compile_definitions(crossguid PUBLIC GUID_LIBUUID PRIVATE GUID_LIBUUID)
	target_link_libraries(crossguid PUBLIC uuid PRIVATE uuid)
endif()

target_include_directories(crossguid PUBLIC . PRIVATE .)


