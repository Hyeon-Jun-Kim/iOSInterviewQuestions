# iOS
###
> Bounds 와 Frame 의 차이점을 설명하시오.
- Bounds와 Frame의 차이점은 View 좌표의 기준점이 다르다는 것입니다.
- Bounds 는 자신의 좌표계를 기준으로 0,0 을 원점으로 설정합니다.
- Frame 은 SuperView의 원점을 0,0 으로 두고 원점으로 얼마나 떨어져있는지를 나타낸 것입니다.
####
> 실제 디바이스가 없을 경우 개발 환경에서 할 수 있는 것과 없는 것을 설명하시오.
- 하드웨어
    * 가속도 센서, 가압계 센서, 주변광 센서, GPS 센서 기능 불가
    * 마우스로 터치를 하기에 두 손가락으로 하는 줌인, 줌아웃을 할 수 없음
    * 카메라, 마이크, 전화기능 불가
- API
    * Apple의 푸시 알림 받기, 보내기 불가
    * 사진, 연락처, 캘린더에 엑세스하기 위한 개인 정보 보호 알림 지원안함
    * Handoff 기능 불가
    * MessageUI 기능 불가
- 그외
    * 네트워크 속도 체크 불가
    * 페이스ID 직업 얼굴 인식을 할 수 없지만 인식됨, 안됨 처리 가능
    * 맥의 성능이 아이폰보다 뛰어나 메모리에 얼마나 큰 부담을 주는지 알 수 없음
####    
> 앱의 콘텐츠나 데이터 자체를 저장/보관하는 특별한 객체를 무엇이라고 하는가?
- UserDefalts
    * 키-값 쌍으로 저장하는 인터페이스이다.
    * 런타임시 개체를 이용하여 기본 데이터베이스에서 사용하는 기본값을 읽어오기 때문에 값이 필요할 때마다 데이터베이스를 열 필요가 없다.
    * 대용량의 데이터보다 자동로그인 여부, 아이디, 환경설정에서의 설정 데이터 값과 같은 단일 데이터 등을 보관한다.
- CoreData
    * 객체 그래프를 관리하기 위한 Framework이다.
    * SQLite와 같이 테이블을 이용하지 않고 객체를 생성하여 데이터를 운영하기에 더 많은 저장공간과 메모리를 필요로 한다. 그렇지만 더욱 빠르게 데이터를 가져온다.
    * Data Model을 생성한 후 Entity를 생성한다.
- SQLite
    * Swift에는 특별한 설치없이 바로 사용할 수 있다.
    * C언어로 작성되어 있기에 매우 가벼운 것이 특징이며, 전체 데이터베이스를 디스크 파일 1개에 저장하고, 설정 자체가 매우 간편하기에 관리하기가 수월하다.
    * SQLite는 iOS, Android, Linux, Window 등과 같이 다양한 운영체제에서 사용된다.
    * 수많은 프로세스와 스레드의 접근으로부터 안전하다.
- Realm
    * SQLite와 같이 오픈소스이며, 모바일에 최적화된 라이브러리이다. SQLite, Core Data보다 속도가 빠르고 성능면에서 더 우수하다.
    * 많은 작업들을 처리하기 위해 코드가 많이 필요하지 않으며, 메인 스레드에서 데이터의 읽기, 쓰기 작업을 모두 할 수 있어 편리하다.
    * 대용량의 데이터에 대해 무료로 사용할 수 있으며, 용량이 적고 큼에 상관없이 속도와 성능이 유지된다.
 ####   
> 앱 화면의 콘텐츠를 표시하는 로직과 관리를 담당하는 객체를 무엇이라고 하는가?
- UIViewController
    * UIKit 앱의 뷰 계층 구조를 관리하는 객체이다.
    * 뷰의 사용자 상호 작용에 응답한다전체 인터페이스의 레이아웃을 관리한다.
    * 앱에서 다른 ViewController를 포함한 다른객체들과 조정을 한다데이터가 변경되면 뷰의 콘텐츠를 업데이트할 수 있다. 
####
> App thinning에 대해서 설명하시오.
- 디바이스에 애플리케이션이 설치될때, 앱스토어와 운영체제가 디바이스에 맞게 설치되도록 설치 최적화 기술을 의미한다. 최소한의 디스크 사용과 빠른 다운로드가 가능하다.

- 슬라이싱
    - 앱이 지원하는 여러 디바이스에 각각의 조각 애플리케이션 번들 생성, 해당 디바이스에 적합한 조각을 전달에 설치한다.
    - 개발자가 앱스토어 커넥트에 앱을 업로드 하면, 앱스토어에서 다양한 버전의 조각들을 생성하고 사용자가 가장 알맞는 조각을 다운로드 하게 해준다
- 비트코드
    - 기계 언어로 번역되기 전단계이다.
    - 비트코드를 사용해서 업로드 하면 애플에서 애플리케이션을 다시 컴파일해서 앱 바이너리 생성한다.
    - 비트코드를 사용하지 않아도, fat binary가 업로드 되기는 하지만 비트코드를 사용하면 다시 컴파일 할 때 최적화 할 수 있다.
- 주문형 리소스
    - 필요할 때만 다운로드 받을 수 있다
    - 예를 들어 체험판 -> 본판
####
> 앱이 시작할 때 main.c 에 있는 UIApplicationMain 함수에 의해서 생성되는 객체는 무엇인가?
- UIApplication 싱글턴 객체가 생성됨
####
> @Main에 대해서 설명하시오.
- 프로그램 실행을 시작하기 위한 진입점
####
> 앱이 foreground에 있을 때와 background에 있을 때 어떤 제약사항이 있나요?
- Foreground mode는 메모리 및 기타 시스템 리소스에 높은 우선순위를 가지며 시스템은 이러한 리소스를 사용할 수 있도록 필요에 따라 background 앱을 종료
- Background mode는 가능한 적은 메모리공간을 사용해야함(시스템 리소스 해제, 메모리에서 해제 후 데이터를 디스크에 작성) 사용자 이벤트를 받기 어렵고 공유 시스템 리소스를 해제하고 이미지 객체 참조 등 메모리 제한
####
> 상태 변화에 따라 다른 동작을 처리하기 위한 앱델리게이트 메서드들을 설명하시오.
- `applicationWillResignActive` 애플리케이션이 InActive 상태로 전환되기 직전에 호출
- `applicationDidEnterBackground` 애플리케이션이 백그라운드 상태로 전환된 뒤 호출
- `applicationWillEnterForeground` 애플리케이션이 Active상태가 되기 전에 호출
- `applicationDidBecomeActive` 애플리케이션이 Active상태로 전환된 후 호출
- `applicationWillTerminate` 애플리케이션이 종료되기 직전에 호출
####
> 앱이 In-Active 상태가 되는 시나리오를 설명하시오.
- 전화나 메시지 같은 인터럽트가 발생하거나, 미리알림 같은 특정 알림창이 화면을 덮어서 앱이 실질적으로 event를 받지 못하는 상태 In-Active 상태가 됨
- 앱을 처음켜거나, foreground에서 background, background에서 foreground 상태가 될 때도 in-Active 상태를 거쳐감
####
> scene delegate에 대해 설명하시오.
- 애플리케이션이 화면에 표시되는 방식과 애플리케이션의 생명주기를 담당함
####
> UIApplication 객체의 컨트롤러 역할은 어디에 구현해야 하는가?
- UIApplicationMain 함수
####
> App의 Not running, Inactive, Active, Background, Suspended에 대해 설명하시오.
- Not Running
    * 앱이 아직 실행되지 않았거나, 완전히 종료되어 동작하지 않는 상태.
- Inactive (Foreground)
    * app이 실행중이지만 사용자로부터 event를 받을 수 없는 상태.
    * multitasking window로 진입하거나 app 실행중 전화, 알림 등에 의해 app을 사용할 수 없게 되는 경우 이 상태로 진입.
- Active (Foreground)
    * 실제 실행중이고 사용자 event를 받아서 상호작용할 수 있는 상태.
    * 바로 Active가 되지 않고 Inactive 상태를 거쳐 Active상태가 된다.
- Background
    * 화면으로 나가거나 다른 app으로 전환되어 현재 app이 실질적인 동작을 하지 않는 상태.
    * 예를 들어 Music app을 닫아도 재생한 음악이 계속 실행되는 경우.
    * 사용자가 app을 사용하지 않는 동안 서버와 데이터를 동기화하거나 타이머가 실행되어야 하는 등의 작업을 이 상태에서 할 수 있습니다.
- Suspended (Background)
    * app을 다시 실행했을 때 최근 작업을 빠르게 로드하기 위해 메모리에 관련 데이터만 저장되어있는 상태.
    * app이 background 상태에 진입했을 때 다른 작업을 하지 않으면 Suspended 상태로 진입하게 됩니다.
    * Suspended 상태의 app들은 iOS의 메모리가 부족해지면 가장 먼저 메모리에서 해제된다.
    * app을 종료시킨 적이 없더라도 app을 다시 실행하려고 하면 처음부터 다시 실행됩니다.
####    
> NSOperationQueue 와 GCD Queue 의 차이점을 설명하시오.
- NSOperationQueue
    * Objective-C 기반 고수준 API
    * GCD보다 약간의 오버헤드가 더 발생되고 느리다. But KVO 지원 및 작업취소등을 지원
    * 다양한 작업들 중에서 의존성을 추가할 수 있다
    * 재사용, 취소, 중지 가능하다
    * NSOperation을 만들어서 병렬 or 직렬로 스레드 풀을 사용가능하다.
- GCD Queue
    * C기반 로우레벨의 API
    * Global Queue에서 QOS 우선순위를 줄 수 있다.
    * Main Queue: 메인 스레드에서 사용될 것 들을 처리, UI코드
####
> GCD API 동작 방식과 필요성에 대해 설명하시오.
- 동작 방식
    * 해야 할 일(코드)을 Operation으로 Wrapping한 다음, Queue에 넣는다.
    * Queue에서 남는 스레드에 작업을 배분한다.
- 필요성
    * 웹에서 이미지를 다운 받아서 사용자에게 보여준다고 했을 때, 비동기로 처리하지 않는다면 이미지를 다운받는 동안 다른 작업을 할 수 없기 때문에 앱이 멈춘다.
    * 이렇게 Cost가 높은 작업을 메인 스레드에서 진행하면 사용자가 다른 작업을 할 수 없기 때문에 필요하다고 생각된다.
####
> Global DispatchQueue 의 Qos 에는 어떤 종류가 있는지, 각각 어떤 의미인지 설명하시오.
- Qos 는 Quiality-of-service(서비스 품질)의 약자이다. 네트워크에서 사용하는 용어로 서비스의 중요도에 따라 자원을 할당하는 것, 또는 이 중요도를 뜻하는 말이다.
- `userInteractive`
    * 가장 높은 우선순위를 뜻함
    * 애니메이션, 이벤트 처리, UI 갱신 등 사용자와의 상호작용을 하는 작업에 이 Qos를 할당
- `userInitiated`
    * 두번째로 높은 우선순위
    * 빠른 반응 속도가 필요하거나, 유저가 앱에 기대하는 핵심 정보를 로딩할 때 등에 사용
- `default`
    * 세번째로 높은 우선 순위이자 기본 값
    * 앱 초기화 혹은 유저를 대신해 수행하는 작업에 사용합니다.
- `utility`
    * default보다 한단계 낮은 우선순위
    * 바로 완료되지 않아도 앱사용에 지장이 없는 부가적인 작업에 사용
- `background`
    * 가장 낮은 우선순위
    * 앱이 백그라운드 상태로 갔을 때 할 작업 등에 사용
####
> iOS 앱을 만들고, User Interface를 구성하는 데 필수적인 프레임워크 이름은 무엇인가?
- UIKit
####
> Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.
- Cocoa Touch framework에 포함되어 있는 프레임워크 중 하나이다.
- String, Int 등의 원시 데이터 타입과 컬렉션 타입 및 운영체제 서비스를 사용해 앱의 기본적인 기능을 관리하는 프레임워크이다.
####
> Delegate란 무엇인지 설명하고, retain 되는지 안되는지 그 이유를 함께 설명하시오.
- delegate란 객체 지향 프로그래밍에서 하나의 객체가 모든 일을 처리하는 것이 아니라 처리해야 할 일 중 일부를 다른 객체에게 넘기는 것을 의미한다.
- retain(유지하다) : 메모리가 해제되지 않아서 낭비되는 현상을 의미 (Memory Leak, 메모리 누수)
- Delegate는 객체 간의 작업이여서 참조 값을 사용하기 때문에 retain 현상이 일어난다.
####
> NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.
- 동작 방식
    * 특정 객체가 NotificationCenter에 등록된 Event를 발생시킴
    * NotificationCennter에 등록된 Observer들 중 해당 Event를 담당 중인 Observer가 그 Event에 대한 행동을 취하는 것(#selector)
- 활용 방안
    * 특정 Event의 실행에 따라 동작해야하는 것
    * 동시적으로 여러 View에서 동작해야하는 것 등을 처리할 때에 활용할 수 있다.
####
> UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?
- Main Thread
- Cocoa Touch 앱에서는 UIApplication의 인스턴스가 main thread에 붙기 때문
- UIApplication은 앱을 시작할 때 인스턴스화 되는 앱의 첫번째 부분인데 앱의 run loop를 포함하여 main event loop를 설정하고 event 처리를 시작한다.
- 앱의 main even loop는 touch, gesture등의 모든 UI Event를 수신한다.
####
> App Bundle의 구조와 역할에 대해 설명하시오.
- 하나의 앱을 구성하는 여러가지 요소(실행파일, 리소스, 컨피규레이션 파일 등)를 한 곳에 묶어서 관리하는 하나의 디렉토리, 모음
####
> 모든 View Controller 객체의 상위 클래스는 무엇이고 그 역할은 무엇인가?
- UIViewController
- 뷰의 내용을 업데이트하고, 뷰와 사용자의 상호 작용에 응답
- 기본 데이터의 변경에 대한 응답으로 뷰의 콘텐츠를 업데이트
- 뷰 크기 조정 및 전체 인터페이스의 레이아웃을 관리
####
> 자신만의 Custom View를 만들려면 어떻게 해야하는지 설명하시오.
- xib 이용해서 별도의 Stroyboard 처럼 관리 가능
    * Xib을 생성하고 또한 별도의 UIView을 상속받은 Class을 생성
    * Xib에서 owner로 해당 클래스를 임명
    * 커스텀 클래스 내에서 초기화 시, Xib 파일을 불러와 view로 임명하는 코드 추가를 하고 원하는 작업들을 Storyboard와 동일하게 수행
- UIView을 상속해서 코드로만 구현
    * UIView을 상속받는 클래스를 생성해 정말 코드로만 원하는 작업들을 설정
####
> View 객체에 대해 설명하시오.
- 화면에 content 표시, 그리기 및 애니메이션, 오토레이아웃, 제스처 인식 등 화면에 관한 것들을 담당하는 객체
- view는 사용자 인터페이스의 기본 구성 요소이며 모든 조작은 main thread에서 해야함
####
> UIView 에서 Layer 객체는 무엇이고 어떤 역할을 담당하는지 설명하시오.
- 렌더링에 사용되는 뷰의 CoreAnimation계층 UIView를 지원해주고 실질적으로 뷰위에 컨텐츠와 애니메이션을 그려주는 역할을 담당
####
> UIWindow 객체의 역할은 무엇인가?
- 사용자 인터페이스에 배경(backdrop)을 제공하고, 중요한 이벤트 처리 행동(behaviors)을 제공
####
> UINavigationController 의 역할이 무엇인지 설명하시오.
- UINavigationController는 앱의 화면 이동에 대한 관리와 그에 연관된 처리를 담당해주는 컨트롤러
- 네비게이션 바와 툴바를 두 가지를 보여주는 역할
- 네비게이션 바에서는 뒤로 가기 버튼과 커스터마이징 한 버튼을 추가할 수 있으며 옵션으로 툴바 뷰도 제공
####
> TableView를 동작 방식과 화면에 Cell을 출력하기 위해 최소한 구현해야 하는 DataSource 메서드를 설명하시오.
- `numberOfRowInSection` : 섹션에 표시할 행의 개수
- `cellForRowAt` : 특정 위치에 표시할 셀을 요청하는 메서드
####
> 하나의 View Controller 코드에서 여러 TableView Controller 역할을 해야 할 경우 어떻게 구분해서 구현해야 하는지 설명하시오.
- 테이블 뷰의 `Tag` 를 등록, 비교해서 구분
- `cellForRowAt` 메서드에서 파라미터로 받는 테이블 뷰를 객체 비교를 통해 구분
####
> setNeedsLayout와 setNeedsDisplay의 차이에 대해 설명하시오.
- setNeedsLayout
    * layoutSubview 메소드를 시스템이 호출하도록 유도함
    * 모든 핸들러가 종료되고 권한이 main run loop로 돌아오는 시점에 view의 position이나 layout에 관한 변화를 적용
- setNeedsDisplay
    * draw 메소드를 시스템이 호출하게끔 유도함
    * 다음 드로잉 사이클이 오면 그 때 쌓여있는 그려야할 컨텐츠들을 동시에 적용
####
> NSCache와 딕셔너리로 캐시를 구성했을때의 차이를 설명하시오.
- 딕셔너리
    * 메모리가 부족하면 값을 삭제하는 코드를 작성
- 캐시
    * Thread-safe
    * 메모리가 자동으로 관리됨
    * 데이터를 쓸때마다 lock을 해줄 필요가 없음
####
> URLSession에 대해서 설명하시오
- 앱과 서버 간 데이터를 주고받기 위해 사용하는 Apple의 기본 API
####
> prepareForReuse에 대해서 설명하시오.
- tableView의 cell을 재사용하기 위해 셀 속성을 reset하는 함수
- dequeueReusableCell 메서드에서 객체가 반환되기 직전에 호출됨
####
> ViewController의 생명주기를 설명하시오.
- `init` : ViewController 객체가 생성됩니다.
- `loadView` : View를 메모리에 로드합니다.
- `viewDidLoad` : View의 Controller가 메모리에 로드된 뒤 호출됩니다.
- `viewWillAppear` : View가 표시되기 직전에 호출됩니다.
- `viewDidAppear` : View가 표시된 후 호출됩니다.
- `viewWillDisappear` : View가 사라지기 직전 호출됩니다.
- `viewDidDisappear` : View가 사라지기 직후 호출됩니다.
- `viewDidUnload` : View가 메모리에서 해제된 뒤 호출됩니다.
####
> TableView와 CollectionView의 차이점을 설명하시오.
- TableView
    * 하나의 열에 여러 행의 cell을 표현하는 방식이기때문에, cell의 모양은 항상 row에 맞춰서 디자인 해야함
- CollectionView
    * 행과 열을 모두 만들 수 있기 때문에 cell의 모양을 자유롭게 디자인이 가능함
