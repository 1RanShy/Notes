[pigpio library](http://abyz.me.uk/rpi/pigpio/cif.html)
![](assets/截图_20230312101533%201.png)
~~~c
//-----------------
set_mode(0, 2, PI_OUTPUT)
gpio_write(0, 2, 1)
~~~

# 编译
## 命令行
![](assets/截图_20230312134819%201.png)
~~~c
g++ -Wall -pthread -o executeable_name project_name.cpp -lpigpio -lrt
//这个是用于只有单个源文件的.
~~~

## CMakeLists
~~~cmake
cmake_minimum_required(VERSION 3.10.0)

#set( CMAKE_CXX_COMPILER "D:/Softwares/C_Compile/mingw64/bin/g++.exe" )  

#set( CMAKE_C_COMPILER "D:/Softwares/C_Compile/mingw64/bin/gcc.exe" )  

project(main)# 工程名 

find_library(WIRINGPI_LIBRARIES NAMES wiringPi)

find_library(PIGPIO_LIBRARIES NAMES pigpio)

include_directories(include) #包含头文件目录

# file(GLOB SOURCE "src/*.cpp" "main.cpp")# 源文件下所有的 cpp文件 和主程序

add_executable(main "main.cpp" "../src/hcsr04.cpp" "../src/TimeUtils.cpp" )

target_link_libraries(main ${WIRINGPI_LIBRARIES})

target_link_libraries(main ${PIGPIO_LIBRARIES})

# 需要执行的cpp才写在这里面 class这种不需要执行的cpp就不用写在这里面
~~~

# Generate PWM Pulse
