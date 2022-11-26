# Autolayout
###
> 오토레이아웃을 코드로 작성하는 방법은 무엇인가? (3가지)
- NSLayoutConstraint 사용
- Visual Format Language 사용
- Anchor 사용
####
> hugging, resistance에 대해서 설명하시오.
- hugging : 우선순위가 클수록 자신의 크기를 유지하려하고, 우선순위가 작을수록 크기가 늘어나는 속성
- resistance: 우선순위가 클수록 자신의 크기를 유지하려하고, 우선순위가 작을수록 크기가 작아지려는 속성
####
> Intrinsic Size에 대해서 설명하시오.
- Intrinsic Size는 콘텐츠의 본질적인 크기입니다.
- 모든 view가 Intrinsic Size를 갖는 것은 아님 (ex : UILabel, UIButton)
- 각각의 view마다 Intrinsic Size가 적용되는 방식이 다름
####
> 스토리보드를 이용했을때의 장단점을 설명하시오.
- 장점
    * UI 구성을 한눈에 확인할 수 있음
    * View에 어떤 속성과 값을 설정했는지 확인하기 쉬움
- 단점 
    * StoryBoard 구현을 위해 Xcode 메모리가 올라감 (기능별로 StoryBoard를 분리하면 해결 가능)
    * 협업시 StoryBoard 충돌 혹은 이슈가 발생할 수 있음
    * 인터페이스빌드와 StoryBoard 간 연결을 추적하기 어려울 수 있음
####
> 코드 기반 UI의 장단점을 설명하시오.
- 장점
    * 스토리보드와 비교했을 때 Xcode가 가벼워짐
    * 협업시 충돌 위험도가 낮아짐
    * 스토리보드에 비해 View의 재사용성이 좋음
- 단점
    * View가 어떤 모습을 갖고 있을지 한눈에 파악하기 어려움
    * View의 속성 및 기능을 숙지하고 있어야함 (스토리보드처럼 기능에 대한 표시를 해주지 않음)
    * NSLayoutConstraint를 통해 AutoLayout을 설정해줘야 하기 때문에 번거로움 (SnapKit 라이브러리를 통해 극복 가능)
####
> Safearea에 대해서 설명하시오.
- 핸드폰의 전체적인 UI를 통틀어서 컨텐츠가 제대로 보일수 있는 부분에만 우리 뷰를 놓을 수 있도록 도와주는 기능
####
> Left Constraint 와 Leading Constraint 의 차이점을 설명하시오.
- Left Constraint : 어떤 객체의 왼쪽
- Leading Constraint : 어떤 객체의 앞쪽 가장자리
####

