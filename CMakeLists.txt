cmake_minimum_required(VERSION 2.8)
project(callpy)
set (CMAKE_BUILD_TYPE Debug)
set(CMAKE_CXX_FLAGS "--std=c++11")

find_package(OpenCV REQUIRED)

include_directories( ${OpenCV_INCLUDE_DIRS})
include_directories(/usr/include/python3.5)	
include_directories(/usr/local/lib/python3.5/dist-packages/numpy/core/include/numpy/)
link_directories(/usr/lib/python3.5/config-3.5m-x86_64-linux-gnu)	    
add_executable(test callpy.cpp)
target_link_libraries(test
		    #   ${Boost_LIBRARIES}
		      /usr/lib/x86_64-linux-gnu/libboost_python-py35.so
		      /usr/lib/x86_64-linux-gnu/libstdc++.so.6
			  /usr/lib/x86_64-linux-gnu/libpython3.5m.so			  
		      )
# install(TARGETS test RUNTIME DESTINATION bin)
add_executable(test1 test1.cpp)
target_link_libraries(test1
			${OpenCV_LIBS}
		    # ${Boost_LIBRARIES}
		    /usr/lib/x86_64-linux-gnu/libboost_python-py35.so
		    /usr/lib/x86_64-linux-gnu/libstdc++.so.6
			/usr/lib/x86_64-linux-gnu/libpython3.5m.so			  
		      )