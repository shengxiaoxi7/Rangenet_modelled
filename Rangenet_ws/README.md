# Rangenet_modelled

1. Cuda11.3安装
官网下载：https://developer.nvidia.com/cuda-toolkit-archive

环境变量配置:

export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-11.3/lib64

export PATH=$PATH:/usr/local/cuda-11.3/bin

export CUDA_HOME=$CUDA_HOME:/usr/local/cuda-11.3

2. cudnn 8.6.0安装
官网下载（需要登陆）：https://developer.nvidia.com/cudnn

将解压出的文件，移动到/usr/local/cuda文件夹下:

sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda-11.3/lib64/

sudo cp  cuda/include/cudnn.h /usr/local/cuda-11.3/include/

3. TensorRT 8.5.3.1安装
官网下载：https://developer.nvidia.com/nvidia-tensorrt-download

4.安装依赖

sudo apt-get update 

sudo apt-get install -yqq  build-essential python3-dev python3-pip apt-utils git cmake libboost-all-dev libyaml-cpp-dev libopencv-dev

sudo apt install python-empy

sudo pip install catkin_tools trollius numpy

5. 运行指令： -p后是预训练模型路径、-s后是要预测点云.bin demo路径

cd ~/catkin_rangenet

./devel/lib/rangenet_lib/infer -p /path/to/the/pretrained/model -s /path/to/the/scan.bin --verbose
