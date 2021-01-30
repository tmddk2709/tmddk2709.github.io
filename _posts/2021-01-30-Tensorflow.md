---
layout: post
title: Tensorflow
categories: Machine Learning
---


### Eager execution

그래프를 생성하지 않고 함수를 바로 실행하는 명령형 프로그래밍 환경

	import tensorflow as tf
	tf.execution_eagerly() #2.0에서는 기본으로 활성화
	
	x = [[2.]]
	m = tf.matmul(x,x)
	print('hello, {}'.format(m)) #hello, [[4.]]

### Gradient Tape

자동 미분을 위한 API. context 안에서 실행된 모든 연산을 테이프에 기록.

	x = tf.ones((2,2))
	
	with tf.GradientTape() as t:
		t.watch()
		y = tf.reduce_sum(x)
		z = tf.multiply(y,y)
	
	# 입력 텐서 x에 대한 z의 도함수
	dz_dx = t.gradient(z,x)
	for i in [0,1]:
	    for j in [0,1]:
	        assert dz_dx[i][j].numpy() == 8.0

