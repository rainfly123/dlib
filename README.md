# dlib

1. How to generate  a statci libary ?          
mkdir build  
cd build       
cmake -DDLIB_NO_GUI_SUPPORT=yes -DDLIB_JPEG_SUPPORT=ON -DCMAKE_C_FLAGS="-O3 -mfpu=neon -fprofile-use -DENABLE_NEON" -DNEON=ON -DCMAKE_C_COMPILER=arm-buildroot-linux-gnueabihf-gcc -DCMAKE_CXX_COMPILER=arm-buildroot-linux-gnueabihf-g++ -DCMAKE_CXX_FLAGS="-std=c++11" ..     
cmake --build . --config Release      

2. How to compile examples?   
cd examples    
arm-buildroot-linux-gnueabihf-g++  -std=c++11 -O3 -I.. -DDLIB_PNG_SUPPORT   face_detection_ex.cpp   ../build/dlib/libdlib.a  -lpthread -lpng
