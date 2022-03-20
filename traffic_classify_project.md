traffic classify project 개요

1. 데이터 준비
  kaggle에서 traffic-signs-processed 데이터를 구글 드라이브에 다운받아서 사용했다.
  데이터의 양이 너무 많아 데이터 파일중 data0.pickle 데이터의 50000개만 training data로 사용했다.
  데이터 형태는 (50000, 3, 32, 32)이며, 32*32크기의 컬러 그림(교통 표지판 그림) 50000개로 이루어져있다.
  그에 맞는 label은 0~42로 총 43개의 라벨이 주어졌다.
  또한 데이터 50000개를 100개의 미니배치 나누어서 트레이닝했다.
  
2. 알고리즘
  이미지 인식에 적합한 CNN알고리즘을 선택했다.
  CNN을 convolution layer 3개, fully-connected layer 2개로 총 5개의 층으로 구성했다.
  convolution layer는 모두 kernel_size=3, stride = 1, padding = 1으로 고정했고,
  풀링으 맥스풀링을 사용했다.
  가중치를 초기화하기 위해 fully-connected layer마다 xavier_uniform 을 사용해서 초기화시켰다.
  
3. 함수 선택
  cost함수로는 crossEntropyLoss를 선택했고, opimizer로는 Adam을 선택했다.
  
