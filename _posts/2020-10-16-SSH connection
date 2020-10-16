---
layout: post
title: SSH connection
categories: Linux
---

## 비밀번호 없이 로그인하기

### SSH Key

로컬(SSH Client)의 public key를 원격(SSH server) 머신의 ~/.ssh/authorized_keys 파일에 추가

클라이언트가 SSH key 를 사용하여 인증을 시도하면 서버는 클라이언트가 private key 를 가지고 있는지 테스트


### SSH 키 생성

    $ ssh-keygen
    $ ssh-copy-id remote@server.com ##key 자동복사
  
### Permission 설정

    $ chmod 700 ~/.ssh
    $ chmod 600 ~/.ssh/authorized_keys
    $ chmod 600 ~/.ssh/id_rsa
    $ chmod 644 ~/.ssh/id_rsa.pub
    $ chmod 644 ~/.ssh/known_hosts
    
  

  
