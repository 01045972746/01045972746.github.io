---
layout: post
title: "Jenkins로 Github 연동하기 (1)"
categories:
  - PlayGround
tags:
  - Jenkins
---
# Jenkins 란?
젠킨스는 CI/CD에 주로 사용되는 오픈 소스 자동화 소프트웨어입니다.  
![placeholder](/assets/image/Jenkins1.png "Jenkins1")  
매번 서버에 배포를 하게 되는 것을 Github이나 스크립트를 이용하여 자동으로 빌드되도록 합니다.  
실제로 저는 `Vue.js` + `Express.js` 로 만든 게시판에 **Jenkins Pipeline** 을 사용하여, 배포 자동화를 구축하였습니다.  
공식 홈페이지 에서는, 설정이 **`쉽다고`** 써있지만 개인적으로 **`미친듯이`** 어려웠습니다.  
다른 분들은 부디 더이상 시간을 낭비하지 않게 블로그에 설정하는 법을 올립니다.

# Jenkins 설치하기
[download]:https://jenkins.io/download/

[다운로드][download] 페이지에 가시면,
![placeholder](/assets/image/Jenkins2.png "Jenkins2")  
LTS 버전으로 자신의 환경에 맞는 파일을 다운 받습니다.  
저는 이미 구축한 `Jenkins` Server가 있기 때문에, Docker로 진행하겠습니다.  
Docker를 이용하면 다음과 같은 명령어로 쉽게 `Jenkins`를 사용할 수 있습니다.

```bash
$ docker pull jenkins/jenkins
$ docker run -p 8080:8080 -p 50000:50000 jenkins/jenkins
$ docker run -itd -p 8080:8080 -p 50000:50000 jenkins/jenkins
# 백그라운드로 실행
```
그리고, 초기 비밀번호를 위해서
```bash
$ docker exec -it jenkins_test cat /var/jenkins_home/secrets/initialAdminPassword
```
를 입력합니다.
![placeholder](/assets/image/Jenkins3.png "Jenkins3")  
이 화면에서 비밀번호를 입력한 후, 로그인을 합니다.  
이후 플러그인 및 Git 설정은 2편에서 설명하도록 하겠습니다.
