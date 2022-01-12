# Yolov5

## colab

필수 드라이브 마운트
```
from  google.colab import drive
drive.mount('/content/drive')
```
1. roboflow에서 데이터를 가져온다.
2. ``` git clone https://github.com/ultralytics/yolov5```
3. ``` pip install -r requirements.txt```
4. yolov5 폴더로 이동 후 ```python train.py --img 416 --batch 80 --epochs 100 --data './data.yaml' --cfg ./models/yolov5s.yaml --weights ./yolov5s.pt ```실행
5. ```python detect.py --weights ./runs/train/exp/weights/best.pt --img 416 --conf 0.4 --source ./test/images```




anaconda 설치
anaconda promopt에서

```
conda install jupyter
```
pytorch, cuda, cnDNN 설치(* 서로 버전이 맞게하는 것이 중요*)

프로젝트 폴더 내에서 pytorch를 설치하면 됨

#pytorch 설치시 python 버전에 맞게 설치 

```
import torch
torch.cuda.get_device_name(0)
torch.cuda.is_available()
```
로 확인 가능

에러시

1. RuntimeError: DataLoader worker ) exited unexpectedly

 -import os
 
 -os.environ['KMP_DUPLICATE_LIB_OK']='True'
 
 2. RuntimeError: Unable to find a valid cuDNN algorithm to run convolution

 - 배치 사이즈 줄이기
