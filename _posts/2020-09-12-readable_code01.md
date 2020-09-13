---
title: Readable Code를 읽으며"
date: 2020-09-12
categories: readable code
---

## 들어가기에 앞서
과거에 작성한 글을 다시 읽어보면서 복기 하는 마음으로 작성하고 있습니다.  
생각보다 재미있네요 ㅋㅋ 이런거 작성할 생각도 했구나.. 싶은 기분도 들고 좀 색다릅니다.  
이 카테고리로 작성하는 글은 Readable Code 라는 책을 읽고 작성하는 감상문 같은 느낌입니다.  
초보 프로그래머일적 작성한 글이기도 하구요..  
이 글이 정답이라 하진 않겠습니다. 각자가 생각하는게 다르니까요.  
본인의 코딩 스타일이나, 팀에서 사용하는 다양한 코딩 룰 사이에 이런 보편적인 방법도 있다는 정도의 참고로 받아 드려주셨으면 좋겠습니다.


## 이름에 정보를 담아라
엔지니어로 일하다 보면 우스갯 소리라도 코딩하는 시간보다 이름 짖는 시간이 더 많다는 말이 있다.  
이게 거짓말 같지만 어느정도 사실에 가깝다고 생각한다.  
혼자 모든 개발을 하는 경우가 아니더라도 코딩을 하는데 있어서 변수나, 메소드 명에 어떤 이름을 붙여야하는지 고민을 많이 할 것이다.  
일을 오랜기간 하다보면 본인만의 스타일이 생기기 마련인데, 팀으로 일하는데 있어서는 어느정도 룰도 있다고 생각한다.  
이 책에서는 아래의 포인트들을 중요시 하고 있다.  
가볍게 라도 한번 참고해보자!!  

#### 특정한 단어를 사용하라 
- 상황에 따라서는 Get 대신 Fetch 나 Download 와 같은 단어를 선택하는 것이 더 이해하기 쉬울수도 있다. 

#### 꼭 그래야 하는 이유가 없다면 tmp나 retval과 같은 보편적인 이름은 피하자 
- 심심찮게 tmp를 남발하는 경우가 있다. (필자..ㅎ) 
- 필요한 곳과, 없어도 되는 곳을 구분하는 것이 중요하다.

#### 대상과 목적을 자세히 묘사하는 이름을 사용하자.
- ServerCanStart() 는 CanListenOpenPort() 와 비교하여 의미가 너무 애매모호 하다.

#### 변수명에 중요한 세부 정보를 덧붙여라
- 미리세컨드를 저장하는 경우엔 변수명 뒤에 ``_ms``를 붙이거나 이스케이핑을 수행하는 변수 앞에는 ``raw_``를 붙이는 것 
- 컴파일 언어(go, java, C등)의 경우에는 변수를 만들 때 이미 어느정도 타입을 알 수 있지만, php나 python같은 인터프리터 언어의 경우 어떤 타입의 값을 이용할 것인지 어느정도 나타내는방식을 사용하면 좋을 것 같다. 

#### 사용 범위가 넓다면 긴 이름을 사용하자 
- 전역변수와 같은 다양한 곳에서 사용되는 변수의 이름을 하나 혹은 두개의 단어로 구성할 경우 어떤 의미인지 이해하기 어려울 수도 있다.
- 다만 짧은 스코프에서 잠깐 사용될 경우 간단히 지어도 상관없을 듯!

#### 대문자나 밑줄 등 다양한 방법으로 의미를 전달하도록 하자.
- 클래스내 지역변수와 전역 변수를 구분하기 위해 ``_``를 사용하는 것도 좋을듯! 
- 필자의 스타일은 ``private``변수 의 경우 접두사로 ``_``를 자주 사용한다.
- 요즘 다양한 언어에서 ``lint``를 많이 지원해준다. 여기서 카멜케이스나, 스네이크케이스 같은 경우를 잘 이용하는것 또한 좋은 방법인것 같다.
    
## 읽기 편한 코드를 작성
갓 엔지니어로 일하기 시작했던 초창기의 경우 코드는 짧으면 짧을 수록 멋지다고 생각했다. ( 지금도 어느정도 이 마인드이다.)  
하지만 무턱대고 짧은 코드 보다는 명확한 의미를 전달하는 짧은 코드가 바로 아름다운 코드가 아닌가 생각한다. 
우리가 스스로 멋진 처리라고 생각한 보편적인 코드는 대부분 내장함수로 지원하는 경우가 많고, 멋들어지게 사용했다고 여기는 무명함수의 남용은 익는이나, 리뷰어의 입장으로선 귀찮기만 할때도 많다.  
코드의 제1 목표는 동작이며, 이후에는 남들이 읽기 편한 코드(유지보수에 유리한)를 작성하는 것, 그리고 마지막이 지나치게 긴 raw를 줄이는 것이 아닐까 생각한다 .  

#### 코드를 읽는 사람이 이미 익숙한, 친숙한 레이아웃을 사용하자

#### 비슷한 코드는 서로 비슷해 보이게 작성하라 

#### 서로 연관된 코드는 하나의 블록으로 묶어라 
- 일관성과 간결성을 위해 줄바꿈과 재정렬을 잘 활용할 것 
- 매소드를 활용하여 불규칙성을 정렬할 것 
- 중복된 코드를 정리할 것 
- 이름이나 에러 문자열 같은 테스트의 중요한 부분은 한눈에 보기 쉽게 모아둘 것 
- 도움이 된다면 코드의 열을 맞추는 것도 좋다.
- 선언문은 블록을 작성 
- 코드를 문단으로 쪼개는 것이 좋다. 

누구나 미학적으로 보기 좋은 코드를 읽고 싶어한다.   
자신의 코드를 일관성 있게 의미있는 방식으로 ``정렬`` 하여 더욱 읽기 편하게 작성할 수 있다.

