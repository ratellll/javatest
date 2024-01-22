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