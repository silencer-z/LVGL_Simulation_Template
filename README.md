# Simulator project for LVGL embedded GUI Library

The [LVGL](https://github.com/lvgl/lvgl) is written mainly for microcontrollers and embedded systems however you can run the library **on your PC** as well without any embedded hardware. The code written on PC can be simply copied when your are using an embedded system.


## 用法

### 获取项目

克隆本项目:

```
git clone https://github.com/silencer-z/LVGL_SIM.git
```

### 安装 SDL
您可以从以下网址下载SDL https://www.libsdl.org/ ,选择最新版本并将其解压缩。


### 安装 GCC编译器
MinGW是windows平台下的GUN编译器，我们需要通过MinGW完成整个程序的编译，这里选择从
https://sourceforge.net/projects/mingw-w64/files/mingw-w64/mingw-w64-release/
下载，划到最下面选择下载`x86_64-posix-seh`。将下载完成的压缩包解压到相应位置，可以选择将
其bin目录添加至系统的环境变量Path中去。也可以选择使用现存的GCC编译器，比如CLion中就自带了MinGW

### 合并MinGW和SDL
LVGL使用SDL来模拟键盘鼠标等驱动输入，我们需要将对应的SDL头文件和库添加到MinGW中去:
将解压后的SDL压缩包内的`cmake`文件夹和`x86_64-w64-mingw32`文件夹直接解压到MinGW解压当中去，使SDL的
`x86_64-w64-mingw32`对应合并。

### SDL静态库

在完成环境设置之后，记得设置IDE的Cmake工具链，编译运行如果不通过，将`SDL2.dll`这个动态库文件拷贝到LVGL工程中的bin目录下
，在模板苦衷已放好，当时为了防止版本不匹配，建议将自己的SDL的dll文件复制到对应位置。

### GUI-Guider 导出

在Gui-guider完成lvgl大体框架的搭建之后，便可以选择导出导出到本项目进行仿真，导出格式设置为RT-thread直接在本目录导出。
