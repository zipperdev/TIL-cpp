## 챕터3

> 📅 **날짜:** 10/26  
> 📖 **페이지:** 79~128p

### 암묵적 자료형 승격

```c++
#include <iostream>
#include <typeinfo>

int main() {
    const bool a = true;
    const char b = 'A';
    const short c = 2025;
    const float d = 3.14;

    // bool -> int
    std::cout << "a + 100: " << a + 100 << " " << typeid(a + 100).name() << std::endl;

    // char -> int
    std::cout << "b + 100: " << b + 100 << " " << typeid(b + 100).name() << std::endl;

    // short -> int
    std::cout << "c + 100: " << c + 100 << " " << typeid(c + 100).name() << std::endl;

    // float -> double
    std::cout << "d + 2.71: " << d + 2.71 << " " << typeid(d + 2.71).name() << std::endl;

    return 0;
}
```

### 암묵적 자료형 변경

```c++
#include <iostream>
#include <typeinfo>

int main() {
    const int a = 100;
    const long b = 2025;
    const double c = 3.14;

    // int + long -> long
    std::cout << "a + b: " << a + b << " " << typeid(a + b).name() << std::endl;

    // int + long + double -> double
    std::cout << "a + b + c: " << a + b + c << " " << typeid(a + b + c).name() << std::endl;

    return 0;
}
```

### 캐스팅

```c++
#include <iostream>

int main() {
    const double a = 3.14;
    const int b = 100;

    std::cout << "without casting: " << a + b << std::endl;
    std::cout << "with casting: " << static_cast<int>(a + b) << std::endl;

    return 0;
}
```

### 정수의 오버플로우와 언더플로우

```c++
#include <iostream>

int main() {
    int num1 = std::numeric_limits<int>::max();
    int num2 = std::numeric_limits<int>::min();
    std::cout << "max: " << num1 << std::endl;
    std::cout << "min: " << num2 << std::endl;

    num1 += 1;
    num2 -= 1;
    std::cout << "max overflow: " << num1 << std::endl;
    std::cout << "min underflow: " << num2 << std::endl;

    return 0;
}
```

### 부동 소수점의 오버플로우와 언더플로우

```c++
#include <iostream>

int main() {
    double num1 = std::numeric_limits<double>::max();
    double num2 = -std::numeric_limits<double>::max();
    std::cout << "max: " << num1 << std::endl;
    std::cout << "min: " << num2 << std::endl;

    num1 *= 100;
    num2 *= 100;
    std::cout << "max overflow: " << num1 << std::endl;
    std::cout << "min underflow: " << num2 << std::endl;

    return 0;
}
```

### 출력 조정자

```c++
#include <iomanip>
#include <iostream>

int main() {
    std::cout << true << std::endl;                                       // 1
    std::cout << std::boolalpha << true << std::noboolalpha << std::endl; // true

    std::cout << std::oct << 1000 << std::endl;                                     // 1750
    std::cout << std::hex << 1000 << std::endl;                                     // 3e8
    std::cout << std::uppercase << 1000 << std::nouppercase << std::endl;           // 3E8
    std::cout << std::oct << std::showbase << 1000 << std::endl;                    // 01750
    std::cout << std::hex << 1000 << std::dec << std::noshowbase << std::endl;      // 0x3e8

    std::cout << 123.45 << std::endl;                                                             // 3.1416e+10
    std::cout << std::fixed << 314.15926535 << std::endl;                                         // 314.159265
    std::cout << std::setprecision(8) << 314.15926535 << std::setprecision(5) << std::endl; // 314.15926535
    std::cout << std::scientific << 314.15926535 << std::defaultfloat << std::endl;               // 3.14159e+02

    std::cout << 2025.0 << std::endl;                                       // 2025
    std::cout << std::showpoint << 2025.0 << std::noshowpoint << std::endl; // 2025.0
    std::cout << std::showpos << 2025.0 << std::noshowpos << std::endl;     // +2025

    std::cout << 123.45 << std::endl;
    std::cout << std::setw(16) << 123.45 << std::endl;
    std::cout << std::setw(16) << std::left << 123.45 << std::endl;
    std::cout << std::setw(16) << std::internal << std::showpos << 123.45 << std::right << std::noshowpos << std::endl;
    std::cout << std::setw(16) << std::setfill('_') << 123.45 << std::setfill(' ') << std::endl;

    return 0;
}
```

### 입력 조정자

```c++
#include <iostream>

int main() {
    int hex;
    int oct;
    bool boolean;

    std::cout << "Enter hex: ";
    std::cin >> std::hex >> hex;

    std::cout << "Enter oct: ";
    std::cin >> std::oct >> oct >> std::dec;

    std::cout << "Enter bool: ";
    std::cin >> std::boolalpha >> boolean >> std::noboolalpha;

    std::cout << std::endl;
    std::cout << hex << std::endl;
    std::cout << oct << std::endl;
    std::cout << boolean << std::endl;

    return 0;
}
```

### 세 자릿수의 정수를 입력받아 역순의 정수 출력

```c++
#include <iostream>

int main() {
    int num;
    std::cout << "Enter three digit number: ";
    std::cin >> num;

    const int firstDigit = num % 10;
    const int secondDigit = num % 100 / 10;
    const int thirdDigit = num / 100;

    const int reversedNum = firstDigit * 100 + secondDigit * 10 + thirdDigit;
    std::cout << reversedNum << std::endl;

    return 0;
}
```

### 시간 주-일-시간 변환

```c++
#include <iostream>

int main() {
    int hour;
    std::cout << "Enter hour(s): ";
    std::cin >> hour;

    const int week = hour / (24 * 7);
    const int day = hour % (24 * 7) / 24;
    const int pureHour = hour % 24;

    std::cout << week << "주 " << day << "일 " << pureHour << "시간" << std::endl;

    return 0;
}
```
