cmake_minimum_required (VERSION 2.8)
 
project (classification_test)
 
add_executable(classification_test main.cpp)
#SET (SRC_LIST main.cpp)
include_directories ( /home/cobot/caffe/include
    /usr/local/include
    /usr/local/cuda/include
    /usr/include )

#使用opencv
find_package(OpenCV REQUIRED)
target_link_libraries(classification_test ${OpenCV_LIBS} )
 
target_link_libraries(classification_test
    /home/cobot/caffe/build/lib/libcaffe.so
    /usr/lib/x86_64-linux-gnu/libglog.so
    /usr/lib/x86_64-linux-gnu/libboost_system.so
    )

#add_library表示编译时在lib文件夹下会生成libclassification.so文件
#如果需要生成.so文件，则需要将上面SET处解除注释
#add_library(so_test SHARED ${SRC_LIST})

