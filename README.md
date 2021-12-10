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
# export PATH=/usr/local/cuda-9.0/bin:$PATH
# export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:$LD_LIBRARY_PATH
```
#cuDNN설치
????

(내컴터 파이썬 버전 확인 필요, 다돌아가면 봄)
#gpu3090의 이름으로 python 3.?버전의 아나콘다 가상환경 생성

```bash
$ conda create -n gpu3090 python=3.? 
#gpu3090의 가상환경으로 이동
$ conda activate gpu3090
```

``` python
#tensorflow 2.4.0 버전 설치
!pip install tensorflow==2.4.0

#tensorflow-gpu 2.4.0 버전 설치
pip install tensorflow-gpu==2.4.0   ->>>>>>>>>requirement로''''''''''

```

# yolov5baseFacilitydetection
```
#학습코드
$ python train.py --img 608 --batch 8 --epochs 50 --data data/coco128.yaml --cfg models/yolov5m.yaml --weights weights/yolov5m.pt

```
