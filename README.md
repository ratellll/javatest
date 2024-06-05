객체는 속성(변수) + 기능 (메소드) 이다 
ex -
class(설계도) Tv{ 

속성(변수)
String color ; // 색
boolean power; // 전원상태
int channel; 채널

기능(메소드)
void power(){
 power !=power;
}
void channelUp(){
channel++;
}
}

객체는 모든 인스턴스를 대표 하는 일반적용어
인스턴스는 특정클래스로부터 생성된 객체  ex- Tv인스턴스

public class가 있는 경우 소스파일의 이름은 반드시 public에 맞춘다 

static이란 메모리가 시작될떄 자리를 받음

캡슐화란 속성과 기능(메소드) 를 하나로 묶어서 필요한 기능을 메서드를 통해 외부에 제공하는것


생성자---
어떠한 객체를 생성하고 나면  변수의 초기값을 설정해야한다.
생성자를 사용하여 초기값 설정을 위한 호출반복을 제거한다
객체는 자기 객체안에서 데이터ㅏ를 변경하는 메서드를 넣는게좋다


-- 만일 멤버 변수와 메서드의 매개변수의 이름이 같으면  매개변수가 우선순위를 가진다 (코드블럭 더 안쪽에 있기떄문에 )
-- 멤버변수에 접근하려면 앞에 this.를 사용하여 접근한다
-- 매개변수의 이름과 맴버 변수의 이름이 같은 경우 `this` 를 사용해서 둘을 명확하게 구분해야 한다.
-- 만일 이름이 같지않은경우 this.를 사용을 하지않아도되지만 사용하는쪽이 좀 더 명확하게 표시할수있다 

* 생성자는 메서드와 비슷하지만 차이가 있다
* 생성자의 이름은 클래스 이름과 같아야 한다.
* 따라서 첫 글자도 대문자로 시작한다. 
* 생성자는 반환 타입이 없다. 비워두어야 한다.
  나머지는 메서드와 같다.

생성자는 중복 호출을 제거할수있고 호출을 필수로하여 비어있는객체르 확실히 체크할수있다
--- 생성자를 사용하면 필수값 입력을 보장할수있다 ---

생성자 this는 생성자 코드에 첫줄에서만 사용이가능하다

*좋은 프로그램은 무한한 자유도가 주어지는 프로그램이 아니라 적절한 제약이 있는 프로그램이다.*

---접근제어자 종류
private : 모든 외부 호출을 막는다.
default : 같은 패키지 안에서 호출은 허용한다
protected : 같은 패키지 호출은 혀용한다. 패키지가 달라도 상속관계의 호출은 허용한다.
public: 모든 호출을 허용한다.

만일 private이라도 내부 public메서드로 접근하고 외부에서 호출이 가능하다

캡슐화의경우 private과 pubilc 을 구분 잘하여 설정한다 

private 경우 클래스안에서 계산하거나 필요할때 묶어둔다
그리고 클라이언트가 사용할만한 기능 말고는 모조리 숨긴다 
------------------------------------------------------------
자바 메모리 

메서드 영역 : 클래스의 정보를 보관한다 . ex) 붕어빵틀
스택영역 : 실제 프로그램이 실행되는 영역이다. 메서드를 실행할 떄마다 하나씩 쌓인다.
힙영역 : 객체(인스턴스)가 생성되는 영역이다. new명령어를 사용하면 이영역에 저장이된다. ex)붕어빵틀을가지고 붕어빵을 만들면 그 붕어빵은 힙영역에 생성이됨

static의경우 힙영역이아닌 메서드영역에 생김 그래서 클래스에 직접적으로 접근하는것처럼 사용 ex) Data.age
static 메서드의 경우도 같은경우다 인스턴스를 만들지않고 바로 접근하여 메서드를 사용할수있다 ex) Data.result 
static의 경우 static이 붙은 변수나 메서드만 사용이가능하다 
왜냐하면 인스턴스는 호출이되야 생성이되고 그때서야 참조값이 생기는데 static의경우 메서드영역에 바로 생성이되니 static으로만 접근이 가능하다



final은 바뀌지않으므로 static과 같이 사용하여 메모리낭비를 방지한다 

final 의 참조 대상의 객체값은 변경할수있다 ex) public으로 만든것


상속이란 부모에게서 공통적인 기능을 부여받는것이라고 생각하는게 좋다
상속은 확장의 개념이라고 생각하면된다  
부모의 기능 + 새로운 클래스의 기능을 사용하는것이니 확장이라고생각하면된다
상속을 받은 클래스를 생성하면 부모도 인스턴스가 생성된다
- 필드와 메서드만 물려받는게아님 


만약 부모의 기능이 맘에들지않아 자식이 새로 정의하는걸 메서드 오버라이딩 이라고 한다 
@Override 어노테이션을 사용하여 혹시나 모를 오류를 방지한다


* 메서드 오버로딩 : 메서드 이름이 같고 매개변수(파라미터)가 다른 메서드를 여러개 정의하는것을 메서드 오버로딩 이라고 한다 .
- 오버로딩은 번역하면 과적인데 , 과하게 물건을 담았다는뜻. 따라서 같은 이름의 메서드를 여러개 정의했다고 이해하면된다.
- ex)    // 정수형 매개변수를 받는 메소드
  public static int add(int a, int b) {
  return a + b;
  }

  // 실수형 매개변수를 받는 메소드
  public static double add(double a, double b) {
  return a + b;
  }

  // 문자열을 이어붙이는 메소드
  public static String add(String a, String b) {
  return a + b;
  }


* 메서드 오버라이딩 : 메서드 오버라이딩은 하위클래스(자식) 에서 상위클래스(부모) 의 메서드를 재정의한다는말이다.
- 따라서 상속관계에서 사용한다.
- 부모의 기능을 자식이 다시 정의하는것이다.
  - Ex)// 부모 클래스
            class Animal {
    // 메소드 정의
    void makeSound() {
    System.out.println("Some generic sound");
 

// 자식 클래스
class Dog extends Animal {
// 메소드 오버라이딩
@Override
void makeSound() {
System.out.println("Bark! Bark!");
 

// 다른 자식 클래스
class Cat extends Animal {
// 메소드 오버라이딩
@Override
void makeSound() {
System.out.println("Meow! Meow!");
 


상속관계의 호출은 결국 자식타입이 부모타입의 기능을 호출할떄 부모입장에서는 외부에서 호출한것과같ㅎㅎㅎ


A가 부모 B가 둘째 C가 막내라고 생각하면
A a = new B()  : A로 업케스팅
B b = new B() : 자신과 같은타입
C c = new B() : 하위타입은 대입할수없음 ----컴파일오류 
C c = (C) new B() : 하위타입으로 다운캐스팅 하지만 B인스턴스에 C와 관련된 부분이 없으므로 잘못된 캐스팅임 

A B C 자신의 상위타입의 인스턴스가 같이 생성되고 하위타입은 생성되지않는다 

만약 extends 를 사용하면 오버라이딩한 메서드가 우선권을 가진다 


추상클래스가 하나라도 있는 클래스는 추상클래스로 선언해야한다 
추상메서드를 상속받은 자식클래스는 반드시 오버라이딩 해서 사용해야한다 

추상클래스안에 모든 메서드가 추상메서드가 되는경우 순수추상클래스라고한다
순수 추상 클래스는  (다형성을 위해 부모타입으로써 껍데기역할만하는것)
- 인스턴스를 생성할수없음
- 상속시 자식은 모든 메서드를 오버라이딩해야됌
- 주로 다형성을 위해 사용됨
- 마치 어떠한 규격을 지켜서 구현해야하는것처럼 느껴짐 (상속을받을경우 필수로 오버라이딩을 해야하ㅇㄴㅇ)


객체지향프로그래밍 은 추상화 캡슐화 상속 다형성으로 만들어진다

객체지향프로그래밍은 프로그램의 명령어 목록이아니라 객체들의 모임으로 생각하면 좋다
 유연하고 변경을 용이하게 만들게된다 ex ) 블럭조립하듯이 , 부품을 갈아끼우듯이

다형성
-- 예를 들어 운전자 - 자동차 
          운전자역할   자동차역할
                        ------자동차구현



OCP 
- Open for extension : 새로운 기능의 추가나 변경사항이 생겼을때 기존코드는 확장할 수 있어야한다
- Closed for modificatio: 기존의 코드는 수정되지 않아야한다.
 확장에는 열려있고 변경에는 닫혀있다는 뜻.

오버로딩같은경우는 매개변수(파라미터) 가  다르거나 반환타입이다르거나
둘다 다르거나 해야한다 (메서드의 이름은 같아야함)


배열이란 참조값의 주소를 넣어주는것이지 배열의값을 넣어두는게아니다 
향상된 포문은 종료조건을 주지않아도된다 .
: 오른쪽에 탐색할 배열을 선택하고 왼쪽에 값을 넣어준다 
배열의 끝에 도착하면  for문이 종료가된다

메서드 사용의 장점 :
- 코드의 재사용 : 메서드는 특정기능을 캡슐화하므로 , 필요할때마다 그기능을 다시 작성할필요없이 메서드를 호출함으로써 코드를 재사용가능케함
- 코드의 가독성 : 이름이 부여된 메서드는 코드가 수행하는 작업을 명확하게 나타내므로 코드를 읽는 사람에게 추가적인 문맥을 제공함
- 모듈성 : 큰 프로그램을 작은 , 관리 가능한 부분으로 나눌수있다. 이늘 코드의 가독성을 향상시키고 디버깅을 쉽게만듬
- 코드 유지관리 : 메서드를 사용하면 코드의 특정부분에서 문제가 발생하거나 업데이트가 필요한경우 해당 메서드만 수정하면 된다
- 추상화 : 메서드를 사용하는곳에서는 메서드의 구현을 몰라도 된다. 프로그램의 다른부분에서는 복잡한 내부작업에대해 알 필요가 없이 메서드를 사용가능함



생성자는 객체생성직후 객체를 초기화하기위한 특별한 메서드라고 생각하면된다.
생성자의 존재이유는 중복적인코드를 제거할수있고 필수호출이기때문에 실수로 호출하지않거나 그럴경우를 방지해준다.
직접 정의한 생성자가 있을경우 반드시 생성자를 호출해야한다. * 필수값 입력을 보장받음
기본 생성자란 매개변수가 없는 생성자



메모리 구조 ---
- 메서드영역 : 클래스의 정보를 보관한다 ex) 붕어빵 틀 , 프로그램을 실행하는데 필요한 공통 데이터를 관리
- 스택영역 : 실제 프로그램들이 실행되는 영역 메서드를 실행할때마다 하나씩쌓임
- 힙영역 : 객체(인스턴스)가 생성되는 영역. new 로 새로 생성한 객체들은 이 영역을 사용


상속
- 상속을 받은 자식의 인스턴스가 생성이되면 부모도 인스턴스가 생성이된다 
- 참조값은 하나지만 실제로 그안에서는 부모와 자식 두가지의 클래스 정보가 공존하는것이다 
- 부모의 생성자 (super)는 무조건 한번은 호출해줘야한다
- 부모의 메서드에 접근할경우 super.*** 으로 꼭 super를 명시해준다