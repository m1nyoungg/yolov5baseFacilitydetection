# background requirement 
 
 
 this project is for the hackton
 
 
```bash
$ git clone https://github.com/ultralytics/yolov5
$ cd yolov5
$ pip install -r requirements.txt
```
#드라이버가 450.36.06버전 이상

#anaconda prompt 실행
```bash
#cuda 설치
$ wget https://developer.download.nvidia.com/compute/cuda/11.0.3/local_installers/cuda_11.0.3_450.51.06_linux.run
$ sudo sh cuda_11.0.3_450.51.06_linux.run
```

```bash
#변수 경로설정

vim ~/.bashrc
# export PATH=/usr/local/cuda-11.0/bin:$PATH
# export LD_LIBRARY_PATH=/usr/local/cuda-11.0/lib64:$LD_LIBRARY_PATH
```
#cuDNN설치
https://developer.nvidia.com/rdp/cudnn-download 에서 8.0 설치

```bash
$ tar -xzvf cudnn-11.0-linux-x64-v8.0.2.39.tgz
$ sudo cp cuda/include/cudnn*.h /usr/local/cuda/include
$ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
$ sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
```
https://gist.github.com/kmhofmann/cee7c0053da8cc09d62d74a6a4c1c5e4 참조



#gpu3090의 이름으로 python 3.?버전의 아나콘다 가상환경 생성

```bash
$ conda create -n gpu3090 python=3.? 
#gpu3090의 가상환경으로 이동
$ conda activate gpu3090
```

``` python
#tensorflow 2.4.0 버전 설치
pip install tensorflow==2.4.0

#tensorflow-gpu 2.4.0 버전 설치
pip install tensorflow-gpu==2.4.0   
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 torchaudio==0.7.2 -f 
```

# yolov5baseFacilitydetection
```
#학습코드
$ python train.py --img 608 --batch 8 --epochs 50 --data data/coco128.yaml --cfg models/yolov5m.yaml --weights weights/yolov5m.pt

```
