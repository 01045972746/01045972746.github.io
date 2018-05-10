---
layout: post
title: "NCP(Naver Cloud Platform) Functions (1)편 - 시작"
categories:
  - PlayGround
tags:
  - Serverless
  - NCP
---
```
웹 크롤링을 위한 단순 Function용 입니다.
```
먼저, `https://www.ncloud.com`에 접속하셔서, 사진과 같이 `Cloud Functions`를 누릅니다.
![placeholder](/assets/image/Main.png "Main")  
  

이것 저것 약관 동의를 하고 나면, 다음과 같은 화면을 볼 수 있습니다.
![placeholder](/assets/image/Console.png "Console")  
  

NCloud Functions는 기본적으로 `Action`, `Trigger`, `Rule`로 이루어져 있습니다. (사용자 가이드)  
`Action`은 실제로 동작하는 `함수`를 작성할 수 있습니다.  
`Trigger`는 `Action`을 동작하게 하는 말 그대로 트리거 입니다.  
`Rule`은 특정한 조건에서만 `Action`이 동작하게 할 수 있습니다.  
  

## Action 만들기  
다음과 같이 왼쪽 메뉴에서 `Action`을 선택해 주세요.  
![placeholder](/assets/image/Action1.png "Action1")  
![placeholder](/assets/image/Action2.png "Action2")  
`Create Action` 버튼을 누르면, 다음과 같은 화면이 뜹니다.  
주요 기능들만 설명 하겠습니다.  
* Name: 무조건 입력해야 쓸 수 있습니다. ( 액션 이름입니다. )
* Package: Action들을 묶어서 같은 프로젝트내의 Action이다 라고 설정할 수 있습니다. (ex Default args)
* language: JS, Java, Python, Swift, PHP 로 사용할 수 있습니다.
* Web: 웹 브라우저로 호출 가능한지 여부를 판단합니다.  
현재 Beta 버전이어서, 브라우저를 통한 GET 호출이 불가합니다. (기본적으로 POST 호출입니다.)
* Default parameters: main함수에 들어갈 기본 인자들 입니다.
* code: 동작할 함수를 기술합니다.  
  
![placeholder](/assets/image/Action3.png "Action3")  
  
  
저는, 해당 `Default parameter`를  
```json
{
  "name": "test",
  "place": "ttt"
}
```
로 주고 실행할 것입니다. 간단하게 기본 코드를 보면,  
```python
def main(args):
  name = args.get("name", "World")
  place = args.get("place", "Naver")
  return {'payload': "Hello," + name + " in " + place + "!"}
```
라는 코드로 파라미터를 받아서, `name`과 `place`를 추출 후에, "Hello, {name} in {place}!" 를 리턴해 주는 함수입니다.  
  
## Action 실행하기  
![placeholder](/assets/image/Action5.png "Action5")  
만들어진 액션을 클릭 후에, 상단의 `Run Action`을 클릭합니다.  
  
![placeholder](/assets/image/Action6.png "Action6")  
다음과 같은 창이 뜨면, `Show results only`를 체크하고 `Run`을 눌러보세요!  
`Runtime parameters`를 지정하지 않았기 때문에, 위에서 지정한 `Default parameter` 값이 들어갔습니다.  
  
![placeholder](/assets/image/Action7.png "Action7")  
`Runtime parameters`를 변경하여 실행시켜 보면, 아주 잘 동작하는 것을 볼 수 있습니다.