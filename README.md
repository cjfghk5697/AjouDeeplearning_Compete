# AjouDeeplearning Compete


## 파일 경로
```bash
Anomaly Detection Competition
│   README.md
│   아주딥러닝대회.pptx
│
└───history
│   │   baseline_CNN.ipynb
│   │   baseline_CNN_center(25.2%  3th).ipynb
│   │   baseline_CNN_center(acc 20%, 2th) .ipynb
│   │	...
│  
│
└───models
│   │	00-20-13-eff4.pth
│   │	00-36-21-eff3.pth
│   │	...
│
└───src
│   │	ops.py
│   │	autoaugment.py
│   │	Train.ipynb
│   │	Tune.ipynb
│   └──	inference_code.ipynb
│
└───img
│   └──	score.png
│
└───input
    │	label_info.txt
    └──	sample_submission.csv
```

## 대회 설명
![image](https://user-images.githubusercontent.com/80466735/181528102-1beb6999-bbfe-4fab-ad8a-cd5727a63bc5.png)
Flower299 dataset에서 crop된 이미지와 noisy가 있는 데이터를 분류하는 대회다. 데이터를 보면 label이 잘못 분류되어 있다.
50 class를 분류하는 vision 대회였다.

[대회 경로](https://www.kaggle.com/c/ajoudeepchallenge2021)

## 모델 요약
- Data Augmentation
  flip, flop, crop 등 다양한 augmentation을 적용했다. 그중에서 mix up augmentation이 가장 좋은 효과를 냈다.
- Model
efficientNet 사용. OOM 문제로 인해 efficientNet B7을 사용하지는 못했지만 deep한 모델일수록 정확도 향상을 보였다.

## 사용법

- 학습시
모든 파일을 clone후 적절한 src/Train.ipynb 파일에 있는 경로를 바꾸면 된다.(데이터셋은 위에 경로에서 다운)

- 모델 평가시
src/Train.ipynb 파일에서 경로 변경 후 사용한다. 여기에 있는 모델을 사용할 경우 models에 있는 파일을 다운받아 사용하면 된다. 

## 느낀점
 대회를 진행하면서 불가능한 분야가 아니라는 것을 느꼈다. 기존까지 대충 뜻만 알았지 자세히 혹은 활용하는 방법이 몰랐던 것들이 많았다. 하지만 이후 내가 어떤걸 공부하고 무엇이 있는지 느끼게한 가장 큰 대회인 거 같다. 이 대회를 위해 100번 넘게 코드를 학습시켜 제출했다. 남들보다 많은 제출 횟수가 내가 얼마나 많은 걸 시도하고 배웠는지 느끼게 해준다. 깊게는 몰랐지만 깊게 공부할 수 있다는 가능성을 보인 대회였다. 
 나중에 파일 정리 방법을 알게되고 다양한 모델을 사용하는 방법을 알게되면 다시 수정해보며 이 대회를 다시 공부해볼 것이다.

## 결론

<private 4th Excellence Award><br>
![화면 캡처 2021-10-01 011238](https://user-images.githubusercontent.com/80466735/135764913-3034f290-651d-4dc9-928b-d25f1c84f279.png)

## Reference
[dacon](https://dacon.io/competitions/official/235697/overview/description) <br>
[Content about noise dataset](https://blog.lunit.io/2017/08/08/deep-learning-is-robust-to-massive-label-noise/) <br>
[paper about noise dataset](https://link.springer.com/chapter/10.1007/978-3-030-58568-6_3)<br>
[mix up code](https://github.com/facebookresearch/mixup-cifar10)<br>
[Pytorch cosineannealingwithwarmup code](https://github.com/katsura-jp/pytorch-cosine-annealing-with-warmup/)<br>
[Pytorch Seed everything](https://www.kaggle.com/bminixhofer/deterministic-neural-networks-using-pytorch)<br>
[Bag of tricks for image classification](https://arxiv.org/abs/1812.01187)
