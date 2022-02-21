# 安裝顯示卡驅動

sudo add-apt-repository ppa:graphics-drivers/ppa

sudo apt update

ubuntu-drivers devices

sudo ubuntu-drivers autoinstall

sudo reboot now

nvidia-smi


# cuda可執行後

sudo apt install freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev

sudo chmod +x cuda_10.0.130_410.48_linux.run

sudo ./cuda_10.0.130_410.48_linux.run -toolkit -samples -silent -override

vim ~/.bashrc

export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
:q

source ~/.bashrc


# 驗證cuda

cd ~/NVIDIA_CUDA-10.0_Samples/5_Simulations/smokeParticles

make clean && make

./smokeParticles 

# 切換gcc

gcc -v   //查看版本

g++ -v   //查看版本

sudo apt-get install -y gcc-7

sudo apt-get install -y g++-7

cd /usr/bin/

sudo rm -r gcc

sudo ln -sf gcc-7 gcc

sudo rm -r g++

sudo ln -sf g++-7 g++


# cuda bashrc

export CUDA_HOME=/usr/local/cuda 

export PATH=$PATH:$CUDA_HOME/bin 

export LD_LIBRARY_PATH=/usr/local/cuda/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

# 查詢cuda版本

cat /usr/local/cuda/version.txt


# 切換cuda

sudo rm -rf /usr/local/cuda  

sudo ln -s /usr/local/cuda-10.1 /usr/local/cuda

# 安裝cudnn

sudo dpkg -i libcudnn7*

sudo apt-get install libfreeimage3 libfreeimage-dev

cp -r /usr/src/cudnn_samples_v7/ ~/

cd cudnn_samples_v7/

cd mnistCUDNN/

make clean && make

![2022-02-21 12-35-34 的螢幕擷圖](https://user-images.githubusercontent.com/67223557/154889866-26de2391-3904-41f9-85e4-e4f968da554c.png)

./mnistCUDNN 

![2022-02-21 12-33-38 的螢幕擷圖](https://user-images.githubusercontent.com/67223557/154889712-d124e2c7-f411-4f10-b895-d930ef1c6859.png)


