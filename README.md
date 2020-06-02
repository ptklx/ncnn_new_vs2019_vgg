# ncnn_new_vs2019_vgg

https://github.com/Tencent/ncnn/wiki/how-to-build#build-for-windows-x64-using-visual-studio-community-2017

参考
下面cmake 编辑的是绝对路径，

cd <ncnn-root-dir>
> mkdir -p build-vs2019
> cd build-vs2019

# cmake option NCNN_VULKAN for enabling vulkan
> cmake -G"NMake Makefiles" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=%cd%/install -DProtobuf_INCLUDE_DIR=<protobuf-root-dir>/build-vs2019/install/include -DProtobuf_LIBRARIES=<protobuf-root-dir>/build-vs2019/install/lib/libprotobuf.lib -DProtobuf_PROTOC_EXECUTABLE=<protobuf-root-dir>/build-vs2019/install/bin/protoc.exe -DNCNN_VULKAN=OFF ..

> nmake
> nmake install

pick build-vs2017/install folder for further usage


cmake -G"NMake Makefiles" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=%cd%/install -DProtobuf_INCLUDE_DIR=C:/Path/to/protobuf-3.4.0/build-vs2019/install/include -DProtobuf_LIBRARIES=C:/Path/to/protobuf-3.4.0/build-vs2019/install/lib/libprotobuf.lib -DProtobuf_PROTOC_EXECUTABLE=C:/Path/to/protobuf-3.4.0/build-vs2019/install/bin/protoc.exe -DNCNN_VULKAN=OFF ..


还有  项目属性   ——> C/C++ ——> 预处理器 ——> 预处理器定义 (此处添加预定义编译开关   NOMINMAX）
_CRT_SECURE_NO_DEPRECATE   
_SCL_SECURE_NO_DEPRECATE   
NOMINMAX
