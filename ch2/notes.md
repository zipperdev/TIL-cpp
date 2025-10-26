## 챕터2 - C++ 프로그래밍 기본

C++ 소스 코드는 토큰과 주석, 2가지 요소로 나눌 수 있다.  
토큰은 식별자, 리터럴, 심볼로 구분할 수 있다.

- **식별자:** 엔티티의 이름.  
  키워드, 미리 정의된 식별자, 사용자 정의 식별자로 구분된다.  
  키워드는 C++에 미리 예약된 식별자이다.  
  미리 정의된 식별자는 키워드와 비슷하지만 재정의할 수 있다. 추천하지 않는다.
- **리터럴:** 자료형을 가진 상수 값.  
  `0`, `"문자열"` 등이 리터럴이다.
- **심볼:** 연산자나 문장 부호로 사용되는 기호.

주석은 다음과 같이 사용 가능하다.
```c++
// 한 줄 주석
/*
여러 줄 주석
*/
```

---

변수는 `자료형 이름;`으로 선언할 수 있으며, 상수는 `const`를 추가해야 한다.
```c++
int a = 20;
const int b = 25;

a = 0;   // ✅
a = 'A'; // ❌
b = 0;   // ❌
```

기본 자료형에는 정수, 부동 소수점, 불, 문자, void, 문자열이 있다.

- **정수**  
  부호 여부를 구분한다. 부호가 없는 경우 `unsigned` 접두사를 사용한다.  
  크기 순으로 `short int`, `int`, `long int`, `long long int`가 있다.
  ```c++
  signed short int a1;
  short int a2;
  short a3;
  
  unsigned long int c1;
  unsigned long c2;
  
  long long int d1;
  long long d2;
  ```
  
  `unsigned`나 `long`, `long long`을 리터럴에 다음과 같이 적용할 수 있다.
  ```c++
  // unsigned
  100u
  2025U
  
  // long
  100l
  2025L
  
  // long long
  100000ll
  20252025LL
  ```
- **부동 소수점**  
  부호 여부를 구분하지 않는다.
  크기 순으로 `float`, `double`, `long double`이 있다.
  ```c++
  float a;
  double b;
  long double c;
  ```

  `float`나 `long double`을 리터럴에 다음과 같이 적용할 수 있다.
  ```c++
  // float
  3.14f
  2.17F
  
  // long double
  3.141592l
  3.718281L
  ```
- **불**  
  참 또는 거짓을 나타낸다.
  ```c++
  bool a = true;
  bool b = false;
  ```
- **문자**  
  하나의 캐릭터를 나타낸다.
  ```c++
  char a = 'A';
  char b = 66;
  ```
- **void**  
  값이 없다.
  ```c++
  void foo() {}
  ```
- **문자열**  
  기본적인 C++의 문자열은 C에서 구현된 자료형으로, null 문자로 끝난다.  
  C++는 새로운 문자열 자료형을 `<string>` 헤더 파일로 제공한다.
  ```c++
  #include <string>
  
  std::string a = "Hello, world!";
  ```
