## 챕터5 - 반복문

후위 표현식과 전위 표현식은 변수를 증감하는 부가 작용을 갖는다.  
후위 표현식은 부가 작용 전의 값, 전위 표현식은 후의 값을 반환한다.
```c++
int a = 0;

std::cout << a++ << std::endl; // 0
a--;
std::cout << ++a << std::endl; // 1
--a;
std::cout << a << std::endl; // 0
```

---

while 반복문은 조건을 반복 평가해, 참이라면 문장을 실행한다.  
카운터 제어, 이벤트 제어 (센티널 제어, 플래그 제어) 반복문 등이 있다.

센티널은 처리 중지를 나타내기 위해 리스트에 존재하는 특별한 항목이다.  
`>>` 연산자로 사용 가능한 EOF 마커가 이에 해당한다.

```c++
int i = 0;
int sum = 0;
while (i < 10) {
    sum += i + 1;
    i++;
}

std::cout << sum << std::endl; // 55
```

---

for 반복문은 카운터 제어 반복문으로 사용한다.  
헤더로 초기화, 조건, 변경 요소를 가지며 `;`로 구분한다.

```c++
int sum = 0;
for (int i = 0; i < 10; i++) {
    sum += i + 1;
}

std::cout << sum << std::endl; // 55
```

---

do-while 반복문은 이벤트 제어 반복문으로 사용한다.  
다른 반복문과 다르게 조건 확인이 실행 후 일어나므로 조건 확인 횟수와 반복 횟수가 같다.

```c++
int num = 4321;
short leftDigit = 0;
do {
    leftDigit = num % 10;
    num /= 10;
} while (num > 0);

std::cout << leftDigit << std::endl; // 4
```
