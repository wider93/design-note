# 목표

문법 후보에 대한 생각들을 (간단하게)정리.

### 타입
##### 불변성, 가변성
* 러스트식으로 가는 거 그렇게 어렵지 않은 것 같음
##### 타입 추론
* 가능하다면 넣어도 좋음.
* 트랜스파일될 언어의 타입 추론에 의존하려면, 생성한 코드를 그 언어로 컴파일까지 해봐야? 하는 게 약간 마음에 걸린다.
##### 스코프, 수명
* 아래 예시가 그렇게 절실해 보이지는 않는다
```rust
let spaces = "   ";
let spaces = spaces.len();
```
* 한편, 같은 이름을 코드 끝까지 쓰는 건 꽤 불편하다. 
* 루프 내에서만 쓰고 없어질 변수 이름 정도는 필요함

### 네이밍컨벤션
* 이름은 짧으면 좋다.
* 그렇지만 축약어가 너무 자주 사용되지 않았으면 좋겠다.
  * 예시: `println`보다 `printline`이 낫고, 그보다 `print(end = '\n')`가 기본인 게 좋은 것 같다.
  * 

### 문자열 

* 포매팅이 편하게, f-string을 기본 모드로
  1. `"{a} {b:.3f} {c:04} {d+e}"`는 편하게 지원 가능
  2. `"{a += b} {c.append(d)} {{{{{e}}}}}"`도 지원해야 하나?
  3. `"{*vec:sep=' ', end = '\n'}"`같은 식은 어떨까 싶다.
* 입출력
  *  scanf, printf처럼 포매팅 범용적이면서, cin, cout처럼 타입 인식 가능하면 좋겠다.
  *  함수가 편할지, 위 3으로 다 해결할지는 이야기해봐야 할듯.
  * `read "{a} {b} {hh}:{mm}:{ss}"`
  * `write "{a} {b} {c:.3f} {d:04}"`
  *  "빠른 입출력"이 기본이 되었으면 좋겠고, 디버그/인터랙티브 시 손쉽게 전환할 수 있었으면 좋겠다.
* 정규식
  * f-string이 디폴트인 동작을 이 용도에서는 빼야 할 것 같은..

### 제어문
* ;을 빼기로 한 김에 indent 이용한 파이썬 스타일로? 
* labeled loop
* `if`->`elif`->`else`는?
* `for/while` -> `else`가 필요할까?
* Bamgo님이 loop에 `finally` 같은 걸 원했던 것 같음
* 예외는?
* 패턴 매칭은?

### 클래스
* a.f() const 가 정의되었을 때 f(a)로 호출할 수 있는 게 좋을까?
* a.f를 f(a)로 호출하는 건?
* a.f(b)를 이항연산자 a f b로 적는 거 상당히 좋아 보였다.
* 빌트인 컨테이너 함수들이 void 대신 자기 자신의 레퍼런스를 리턴하는 게 더 편하지 않을까 싶다.
* `x.sort(key = first).sort(key = second)`
* 추상화가 용이하고 비싸지 않으면 좋겠는데 방법은 잘 모르겠다.

### 라이브러리 제공
* std에 없지만 훨씬 빠른 자료형이 많은데 많이 갖다 두면 좋겠다.
