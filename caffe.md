【caffe编译】 fatal error: hdf5.h: 没有那个文件或目录
查找文件  
locate hdf5.h  
修改Makefile.config文件，在下面的语句后面增加红色部分  
INCLUDE_DIRS := $(PYTHON_INCLUDE) /usr/local/include /usr/include/hdf5/serial/

Makefile中修改为  
LIBRARIES += glog gflags protobuf boost_system boost_filesystem m hdf5_serial_hl hdf5_serial  

清理编译  
make clean  
重新编译
