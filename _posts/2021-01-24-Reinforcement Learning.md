---
layout: post
title: Reinforcement Learning
categories: Machine Learning
---

# 환경 설저

## conda 명령어에서 오류 발생하는 경우 : ~/.bash_profile에 아래 내용 추가

    export PATH="/opt/anaconda3/bin:$PATH"
  

## 가상환경
    
    conda create --name "가상환경명" python="파이썬버전" 
    conda remove --name "가상환경명" --all
    conda activate "가상환경명"
    
    conda info --envs ### 현재 생성된 가상환경 확인
    
    
## tensorflow, gym 설치
    
    # tensorflow는 python=3.7에서!
    conda install tensorflow
    pip install gym
