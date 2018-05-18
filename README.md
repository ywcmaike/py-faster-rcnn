py-faster-rcnn without gpu (only cpu)

This version forks from the py-faster-rcnn(the rbg's code), and modify some files to adapt my environment withdout gpu. The modified file is different from the primary file,and renamed with the suffix ".bak". If you want to run this version, and reproduce, you can fork from the py-faster-rcnn, and modify likes what I have done. By the way, you can just fork this version, because I have reproduce this algorithm on my computer. Besides, run some originate scipt to download the model withdout vpn may be imposible. So I have downloaded the model and push it. (本版本拷贝于rbg大神的py-faster-rcnn, 然后修改部分文件去适应我没有gpu的环境。修改的文件和原来的文件不同，在原来文件增加后缀.bak 以区分。 如果你想运行此版本并重现，你可以拷贝rbg大神的版本，然后像我一样修改相关文件。顺便一提，你可以直接拷贝此版本，因为我已经重现此算法在我的电脑上。另外，在没有vpn的环境，运行原来的脚本去下载模型，可能不可能，我已经下载好模型且上传。）

Requirement or Environment: 
ubuntu 16.04 only cpu, opencv3.3, python2.7, cmake3.8.


Modify list:
1. Makefile.config 
1)cp Makefile.config.example Makefile.config
2)modify the Makefile.config as followed;
 CPU_ONLY := 1
 OPENCV_VERSION := 3
 WITH_PYTHON_LAYER := 1
 INCLUDE_DIRS := $(PYTHON_INCLUDE) /usr/local/include /usr/include/hdf5/serial
 LIBRARY_DIRS := $(PYTHON_LIB) /usr/local/lib /usr/lib /usr/lib/i386-linux-gnu/hdf5/serial /usr/lib/x86_64-linux-gnu /usr/lib/x86_64-linux-gnu/hdf5/serial

2.cd $FRCN_ROOT/lib
  make
3.cd $RFRCN_ROOT/caffe-faster-rcnn
  make -j8 && make pycaffe
4. cd $FRCN_ROOT
  ./data/scripts/fetch_faster_rcnn_models.sh
5. cd $FRCN_ROOT
   ./tools.demo.py


 the model and the dataset can be downloaded from here.
链接: https://pan.baidu.com/s/1tNRFuK_IQkyfi4AhaO3waw 密码: 4fe1
