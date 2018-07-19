##【caffe编译】   

Note：有英文水平的建议直接阅读官方安装手册，浅显易懂。

###1、Cmake编译方法：  
官方文档：https://github.com/BVLC/caffe/pull/1667
a、cmake -DCMAKE_BUILD_TYPE=Release/Debug -DCPU_ONLY=NO/ON -DCMAKE_INSTALL_PREFIX=/usr/local ..

###2、Makefile编译
官方文档：http://caffe.berkeleyvision.org/installation.html#compilation
a、cp Makefile.config.example Makefile.config
b、修改Makefile.config
For CPU & GPU accelerated Caffe, no changes are needed.
For cuDNN acceleration using NVIDIA’s proprietary cuDNN software, uncomment the USE_CUDNN := 1 switch in Makefile.config. cuDNN is sometimes but not always faster than Caffe’s GPU acceleration.
For CPU-only Caffe, uncomment CPU_ONLY := 1 in Makefile.config.

c、编译  
make all  
make test  
make runtest  

d、问题及修复：  
fatal error: hdf5.h: 没有那个文件或目录
查找文件  
locate hdf5.h  
修改Makefile.config文件，在下面的语句后面增加红色部分  
INCLUDE_DIRS := $(PYTHON_INCLUDE) /usr/local/include /usr/include/hdf5/serial/

Makefile中修改为  
LIBRARIES += glog gflags protobuf boost_system boost_filesystem m hdf5_serial_hl hdf5_serial  

清理编译  
make clean  
重新编译
