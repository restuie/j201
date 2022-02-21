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

./mnistCUDNN 

# 安裝python3

sudo apt install python3-dev python3-pip python3-venv

sudo apt install python3-virtualenv

python3 -m venv --system-site-packages ./venv #設定python虛擬環境1

virtualenv --system-site-packages --python=/usr/bin/python3.6 ./venv1 #設定python虛擬環境2

source ./venv/bin/activate ＃進入虛擬環境

pip install --upgrade pip ＃進入環境後先升級pip

# python版本 cuda cudnn tensorflow對照

https://www.tensorflow.org/install/source#linux


![2022-02-21 16-11-03 的螢幕擷圖](https://user-images.githubusercontent.com/67223557/154914482-726aedaa-dca7-4d6c-bfae-cb66ab01ba3b.png)


# 安裝其他版本的python

![2022-02-21 16-33-07 的螢幕擷圖](https://user-images.githubusercontent.com/67223557/154917537-b0982614-6205-4608-b341-b33280910e06.png)


# 安裝tensorflow問題

![2022-02-21 17-10-03 的螢幕擷圖](https://user-images.githubusercontent.com/67223557/154923578-c869dd7d-5bf8-4306-8c1d-24162c379589.png)

![2022-02-21 17-48-16 的螢幕擷圖](https://user-images.githubusercontent.com/67223557/154930090-226f763d-f6a8-42e5-96f7-17921245abba.png)




