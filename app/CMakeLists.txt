cmake_minimum_required(VERSION 3.4.1)

set(pathTpProject D:/Android/AndroidStudioProjects/facedetection)
set(pathToOpenCv D:/Administrator/Downloads/opencv-3.4.3-android-sdk/OpenCV-android-sdk )
set(OpenCV_DIR ${pathToOpenCv}/sdk/native/jni)
find_package(OpenCV REQUIRED)
include_directories( ${pathToOpenCv}/sdk/native/jni/include)

#声明库名称、类型、源码文件
add_library(native-lib
            SHARED
             src/main/cpp/native-lib.cpp)

find_library( log-lib
              log )

target_link_libraries( native-lib
                       ${log-lib}
                       ${OpenCV_LIBS})
