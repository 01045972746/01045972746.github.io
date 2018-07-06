---
layout: post
title: "Jenkins로 Github 연동하기 (2)"
categories:
  - PlayGround
tags:
  - Jenkins
---
# Jenkins 플러그인 설치하기
**`Jenkins`** 에는 수많은 플러그인들이 있습니다. 그 중 제일 필요한 것은 Github, SSH 등의 플러그인 입니다. Version 2.x 버전 이후에
![placeholder](/assets/image/Jenkins4.png "Jenkins4")  
`Install suggested plugins` 를 선택하면, 필수 플러그인들을 설치해 줍니다.  
![placeholder](/assets/image/Jenkins5.png "Jenkins5")  


# Jenkins 계정 생성하기
![placeholder](/assets/image/Jenkins6.png "Jenkins6")  
플러그인 설치 직후, 다음과 같은 페이지가 나옵니다.  
Admin 계정을 생성하고 다음 단계로 넘어갑니다.  

# Jenkins 설정하기
![placeholder](/assets/image/Jenkins7.png "Jenkins7")  
해당 설정값은 서버의 도메인이나 호스트가 있을 경우 설정을 달리 해주시면 됩니다. 저 같은 경우는, Docker로 구성했기 때문에 Default로 하였습니다.

# Git 설정하기
![placeholder](/assets/image/Jenkins8.png "Jenkins8")  
앞선 단계를 성공적으로 거치셨다면, 위와 같은 화면을 보실 수 있습니다.  
먼저 `새로운 Item`을 눌러, 프로젝트를 생성합니다.  
![placeholder](/assets/image/Jenkins9.png "Jenkins9")  
Freestyle project를 눌러서 새 프로젝트를 생성합니다.  
![placeholder](/assets/image/Jenkins10.png "Jenkins10")  
설정의 중간쯤, `소스 코드 관리` 부분에 **`Git`**을 누릅니다.  

# Credentials 설정하기

