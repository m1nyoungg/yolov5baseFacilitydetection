# background requirement 
 해당 프로젝트는 CUDA 10.2에서 진행되었지만, 심사용 컴퓨터 환경에 맞춰 11.0으로 세팅함. 
그래픽 드라이버가 450.36.06 버전 이상시 진행

### STEP 01 CUDA 11.0, cuDNN 8.0 install
CUDA
```bash
 #cuda 설치
$ wget https://developer.download.nvidia.com/compute/cuda/11.0.3/local_installers/cuda_11.0.3_450.51.06_linux.run
$ sudo sh cuda_11.0.3_450.51.06_linux.run
```
```
#cuda 경로설정
vim ~/.bashrc
# export PATH=/usr/local/cuda-11.0/bin:$PATH
# export LD_LIBRARY_PATH=/usr/local/cuda-11.0/lib64:$LD_LIBRARY_PATH
```

cuDNN
https://developer.nvidia.com/rdp/cudnn-download 에서 8.0 설치


```bash
$ tar -xzvf cudnn-11.0-linux-x64-v8.0.2.39.tgz
$ sudo cp cuda/include/cudnn*.h /usr/local/cuda/include
$ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
$ sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
```

### STEP 02 anaconda install
#가상환경 설정을 위해 아나콘다 설치 
https://www.anaconda.com/products/individual
```bash
$ conda create -n gpu3090 python=3.? 
#gpu3090의 가상환경으로 이동
$ conda activate gpu3090
```

### STEP 03 Torch and python requirement install
``` python
#추가 토치환경 설치
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 torchaudio==0.7.2 -f 
pip install -r requirements.txt
```

# yolov5baseFacilitydetection
```
#학습코드
$ python train.py --img 608 --batch 8 --epochs 50 --data data/coco128.yaml --cfg models/yolov5m.yaml --weights weights/yolov5m.pt

```
