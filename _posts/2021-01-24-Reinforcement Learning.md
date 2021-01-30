---
layout: post
title: Reinforcement Learning
categories: Machine Learning
---

# 환경 설정

## conda 명령어에서 오류 발생하는 경우 : ~/.bash_profile에 아래 내용 추가

    export PATH="/opt/anaconda3/bin:$PATH"
  

## 가상환경
    
    conda create --name "가상환경명" python="파이썬버전" 
    conda remove --name "가상환경명" --all
    conda activate "가상환경명"
    
    conda info --envs ### 현재 생성된 가상환경 확인
    
    # tensorflow는 python=3.7에서!
    conda install tensorflow
    conda install tensorflow==1.15
    pip install gym

    # jupyter lab
    conda install ipykernel
    python -m ipykernel install --user --name "가상환경이름" [--display-name="<jupyterlab에서 보이고 싶은 커널 이름>"]
