---
layout: post
title: "골빈 해커의 3분 딥러닝∥01 - Basic.py 공부"
date: 2018-04-05
image: ''
description: 'Deep Learning Study'
tags:
- python
- Deep Learning
- Machine Learning
categories:
- python
- Study
description: 
---
참고 : [골빈 해커의 3분 딥러닝](https://github.com/golbin/TensorFlow-Tutorials/tree/master/03%20-%20TensorFlow%20Basic)
>*이 글은 전문지식이 갖춰지지 않은 상태로 텐서플로우를 접한 사용자가 이해한 내용이므로, 앞으로 지식이 쌓이면 수정하려고 한다.*

파이썬 문법을 공부함과 동시에 딥 러닝 라이브러리인 텐서플로우를 같이 공부하려고 검색한 결과, 좋은 예제로 익히기 쉬운 서적을 발견하였고, 해외에 있어서 비록 책을 구입해서 자세한 설명을 보는 것은 어렵겠지만, 그래도 나름 소스코드 해석을 하면서 이해 해 보려고 한다.

우선 현재 개발 환경은 아래와 같다.
>OS : Windows 10
Python : 3.5
Anaconda : Anaconda3 4.2

아나콘다에서 제공하는 아나콘다 명령 프롬프트에서 대부분의 작업을 진행, 파이썬 소스코드 수정은 VS Code 를 이용하여 수정하려고 한다.*가장 편해서.*
- - -
**Anaconda Prompt**를 관리자 모드로 연 후 01-Basic.py 예제대로 학습을 진행해 보았다. 아래는 소스코드을 본인 나름대로 해석해보고 써내려간 글이다.
```
import tensor flow as tf
``` 
텐서플로우를 tf라는 인자(변수)로 불러들이는것 같다. 실제로 tf가 아닌 다른 이름으로 해도 실행이 되었다
```import tensor flow as yh``` 로 한번 해보았다.


```
hello = tf.constant(“Hello, Wow!”)
```
 .constant는 말그대로 상수이다. 여기서 tf는 위에서 할당한 인자의 이름이고 yh로 설정했다면``` yh.constant()```를 쓰는것으로 정상적으로 작동한다.
 파이썬에서 구동중이므로 파이썬 기본 문법이 통용되는 듯 하다. **“ "**를 쓰든 **’ ‘**를 쓰든 문자열로 인식한다.
어쨌든 hello라는 변수를 선언하고 ```"Hello, Wow!"```라는 문자열을 대입했다.


```
print(hello)
```
기본적으로 파이썬에서 변수를 출력하는 함수로 print를 쓰지만, 텐서플로우에서는 약간 다르다. 이 명령어를 입력하면 아래와 같은 결과값이 나온다
```Tensor("Const:0”, shape=(), dtype=string)```
딥러닝을 하고있는 대학원생 친구에게 물어보니, 텐서플로우는 그래프 언어라 값을 찍어보려면 다른 형태로 출력을 해야한다고 한다. 자세한 정보는 구글링


```
a = tf.constant(10)
b = tf.constant(32)
c = tf.add(a, b)  # a + b 로도 쓸 수 있음
```
 hello 변수와 같은 형식으로 a, b변수에 int 값을 대입한 후, c에는 constant가 아닌 add를 사용하여 값을 할당.


```
sess = tf.Session()
```
Session객체와 run메소드를 사용할 때 계산이 되므로 그래프를 실행할 세션을 구성한다.


```
print(sess.run(hello))
print(sess.run([a,b,c])
```
 sess.run : 설정한 텐서 그래프(변수나 수식 등)을 실행(출력)한다
```
sess.close()
```
 세션을 닫는다.

- - - 

베이직이므로 정말 기초적인 구문들만 다룬 듯 하다. 다음장으로 넘어가자.
