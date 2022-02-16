# cuda可執行後

sudo apt install freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev

sudo chmod +x cuda_10.0.130_410.48_linux.run

sudo ./cuda_10.0.130_410.48_linux.run -toolkit -samples -silent -override

vim ~/.bashrc

export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
:q

source ~/.bashrc
