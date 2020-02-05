---
layout: post
title: "Python 개발환경 구축∥python 3.5, Anaconda3 4.2 설치 Windows 10"
date: 2018-04-05
image: ''
description: ''
tags:
- python 3.5
- Anaconda3 4.2
- Windows 10
- Python
categories:
- Deep Learning
description: 
---

요즘 하루의 마무리를 연구실에서 보내고 있다.

아직 학기가 시작되기 일주일 정도의 시간이 남아, 학기 시작 전에 미리 개발환경을 구축해두려고 고군분투 중이다.

아직 연구실에서 정확히 무슨 연구를 할 지는 잘 모르겠으나 일단 파이썬을 배워보자 라는 생각을 예전부터 가지고 있어서, 도서관에서 관련 서적 등을 대출해서 읽는 중인데 책마다 개발환경 구축 방법이 가지각색이어서 여러 정보를 취합해서 나만의 설치방법을 블로그에다가 남겨두려한다.

조만간 데스크탑이아닌 노트북을 지급받을텐데, 노트북에서도 같은 개발환경이 구축되기 원활하도록 남겨두는것이다.
* * *
우선 아나콘다를 설치하면 파이썬이 자동으로 설치되므로, 사전에 파이썬을 설치하는 등의 행동은 금하도록 하자.

하지만 디렉토리 관리로 기존 설치된 파이썬을 건드리지 않는 방법으로 아나콘다를 이용할 수 있다고한다. 하지만 매우 귀찮을 듯 하여 파이썬을 모두 삭제 후 아나콘다 설치.

차라리 아나콘다 내에서 **conda** 를 사용하여 다른 파이썬 버전을 사용하는 것을 택하자

## 아나콘다 설치
>설치 링크 : [아나콘다 구버전 Install](https://repo.continuum.io/archive/)
>
설치 링크에서 Anaconda3 4.2 를 다운받고 설치한다. 아나콘다 뒤에있는 숫자는 파이썬의 버전을 이야기하는것같다.

처음에 실수해서 4.2버전을 찾아서 설치했지만, 알고보니 Anaconda2 였고, 파이썬 버전 확인(python -V or python -version)을하니 python2.X가 깔려있어서 조금 당황. 하지만 평정심을 찾고 다시 Anaconda3을 설치

**아나콘다**를 설치 후, **텐서플로우**를 사용할 가상환경을 만들어준다.

우선 **Anaconda Prompt** 를 관리자로 실행하여 터미널을 구동해준다. *윈도우라면 **cmd** 혹은 **Window PowerShell** 관리자로 구동가능, 아무 디렉토리에서 conda를 이용하여 가상환경을 만든다.

우선 터미널 창에서 **콘다**를 업데이트
```
$ conda update conda
# 콘다가 자신을 업데이트하는것을 볼 수 있다.
```

그리고 다음과 같이 가상환경을 생성해준다.
```
$ conda create -n (name) python = 3.5 anaconda
```

(name)에는 본인의 취향에 맞게 가상환경의 이름을 써준다. 나는 텐서플로우를 사용하기 위하여 tensorflow 로 해주었다가 알수없는 오류로 인하여 tensor1으로 구축. 혹여나 다른 문제가 생기면 tensor2를 새로 만들어서 사용할 예정이다. 파이썬의 버전은 3.5 로 설정. 이전에 아나콘다 최신판을 설치한 후에 텐서플로우를 설치해보았는다, 파이썬 버전이 최신버전(아마 3.6.x)여서 텐서플로우 설치가 불가능했었다. (다른 블로그에서는 최신파이썬버전도 대응을 한다고 써져있었는데 본인 컴퓨터에서는 안되었으므로, 일단 100% 신뢰가 가는 파이썬 3.5를 설치해보았더니 문제없이 구동되었다. 자세한 정보는 텐서플로우 공식홈페이지를 확인하자. 영어로 써져있지만)

그리고 뒤에 anaconda 를 써두었는데, 본인은 anaconda 를 안적은채로 설치하였다. 다른 블로그를 보니, anaconda가 설치된 디렉토리 밑에 /anaconda/envs/testvirenv 라는 디렉토리가 생성되면서 그 안에 필요한 것들을 설치하겠냐고 묻는다고 한다. 여러번의 파이썬 재설치와 아나콘다 재설치로 피곤해진 나는 anaconda를 입력하지 않은채 그대로 conda를 실행했다. 별 문제 없는듯 하다.

이 후, 가상환경(tensor1)을 구동시켜서 텐서플로우를 설치하도록 하자
```
$ activate tensor1 
# 나는 tensor1이란 이름으로 가상환경을 만들었다
```
이러면 터미널창에 ```(tensor1) C:\Windows\system32> ```이런식으로 표시가 된다. (터미널 창에서의 복사는 Ctrl + C 가 아닌 Ctrl + Ins)

만약 가상환경에서 벗어나 현실세계로 돌아오고싶다면 아래의 명령어를 입력하면 된다
```
$ deactivate tensor1
```
여기서 의문점이 드는게, 가상환경 tensor1 을 activate 시켰을때, ```(C:\Anaconda3)이 (tensor1)```으로 바뀌고, deactivate를 시키면  ```(C:\Anaconda3```)로 돌아오긴 커녕 그냥 보통 cmd 나 Window PowerShell 터미널창과 똑같은 환경이 된다. 아나콘다도 동시에 deactivate 되는건가? 귀찮아서 정보검색을 하지 않고 그냥 아나콘다 명령프롬프트를 재시작 하는걸로 쇼부쳤다.

가상환경을 구동시키기 전에 pip을 업데이트 해주도록 하자
```
$ python -m pip install --upgrade pip 
# conda와 마찬가지로 pip이 pip을 업그레이드 한다. 웃기다
```
이미 최신 패키지 버전인 경우에는

```Requirement already up-to-date: .... ```

다시 ```$ activate tensor1``` 으로 가상환경으로 진입 후 tensorflow 를 pip을 통해 인스톨해준다.
```
$ pip install tensorflow
# tensorflow_gpu도 있는듯 하다만 오류가 나서 다시 초기화 시킨 후 순정tensorflow를 재설치하였다.
```

별문제가 없이 인스톨이 완료되었다면 파이썬에서 텐서플로우를 임포트 해보자
```python
$ python
>>> import tensorflow
>>>
```
이렇게 되면 텐서플로우가 무사히 설치된거라고 한다.
사실 잘 모르겠지만 일단 실행이 되므로.



인터넷에서 텐서플로우 공부 예제를 검색해서 아래 사이트를 통해 학습 중이다.

https://github.com/golbin/TensorFlow-Tutorials/
깃허브의 사용법은 아직도 잘 모르겠다.

예전에 git을 깔아놨기 때문에 git clone으로 튜토리얼 프로젝트 파일을 다운로드 해준다.
```
$ git clone https://github.com/golbin/TensorFlow-Tutorials.git
```
이렇게 치면 클론으로 예제를 받을 수 있는듯
그런다음 터미널이나 명령프롬프트에서 TensorFlow-Tutorials / 03 - TensorFlow Basic 위치로 이동한 뒤 다음 명령어를 실행해본다.
>여기서 문제점이 발생, 파일 공백을 인식못하는듯하여, 나는 파이썬 파일 이름을 01.py, 02.py, 03.py로 바꿔서 실행해보았다.```

```
$ python 01.py
Tensor("Const:0", shape=(), dtype=string) 
Tensor("Add:0", shape=(), dtype=int32) 
b'Hello, TensorFlow!' 
[10, 32, 42]
```
이렇게 실행이 되면 텐서플로우가 정상적으로 설치 되었다고 보면 된다고 한다.



오늘은 여기까지
