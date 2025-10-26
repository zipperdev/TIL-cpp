## 챕터2 예제

> 📅 **날짜:** 10/24  
> 📖 **페이지:** 23~78p

### 시간, 분, 초 단위를 입력받아 초 단위로 환산

```c++
#include <iostream>

int main() {
    unsigned int hour;
    unsigned int min;
    unsigned int sec;

    std::cout << "Enter hour(s): ";
    std::cin >> hour;
    std::cout << "Enter minute(s): ";
    std::cin >> min;
    std::cout << "Enter second(s): ";
    std::cin >> sec;

    unsigned int totalSec;
    totalSec += hour * 60 * 60;
    totalSec += min * 60;
    totalSec += sec;

    std::cout << totalSec << std::endl;

    return 0;
}
```

### 정사각형 변을 입력받아 넓이와 둘레 계산

```c++
#include <iostream>

int main() {
    unsigned int side;
    std::cout << "Enter square side length: ";
    std::cin >> side;

    const unsigned int area = side * side;
    const unsigned int perim = 4 * side;
    std::cout << "Area = " << area << std::endl;
    std::cout << "Perimeter = " << perim << std::endl;

    return 0;
}
```
