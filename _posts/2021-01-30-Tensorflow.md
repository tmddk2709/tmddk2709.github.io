---
layout: post
title: Tensorflow
categories: Machine Learning
---

**Eager execution**

그래프를 생성하지 않고 함수를 바로 실행하는 명령형 프로그래밍 환경

	import tensorflow as tf
	tf.execution_eagerly() #2.0에서는 기본으로 활성화
	
	x = [[2.]]
	m = tf.matmul(x,x)
	print('hello, {}'.format(m)) #hello, [[4.]]


