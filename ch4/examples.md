## 챕터4

> 📅 **날짜:** 10/26  
> 📖 **페이지:** 129~168p

### 세 정수 중 최솟값 구하기
```c++
#include <iostream>

int main() {
    int num1, num2, num3;
    std::cout << "Enter first num: ";
    std::cin >> num1;
    std::cout << "Enter second num: ";
    std::cin >> num2;
    std::cout << "Enter third num: ";
    std::cin >> num3;

    int min = num1;
    if (num2 < min) min = num2;
    if (num3 < min) min = num3;

    std::cout << min;

    return 0;
}
```

### 차량 종류와 주차 시간을 입력받아 요금 계산하기

```c++
#include <iostream>

int main() {
    char type;
    int hour;
    std::cout << "Enter vehicle type (c(ar) | b(us) | t(ruck)): ";
    std::cin >> type;
    std::cout << "Enter parked hour(s): ";
    std::cin >> hour;

    int cost;
    switch (type) {
        case 'c':
            cost = hour * 2;
            break;
        case 'b':
            cost = hour * 3;
            break;
        case 't':
            cost = hour * 4;
            break;
        default:
            std::cout << "Unknown vehicle type." << std::endl;
            return 1;
    }

    std::cout << cost << "$" << std::endl;

    return 0;
}
```

### 세 점수를 입력받아 학점 구하기

```c++
#include <iostream>

int main() {
    int score1, score2, score3;
    std::cout << "Enter first score: ";
    std::cin >> score1;
    std::cout << "Enter second score: ";
    std::cin >> score2;
    std::cout << "Enter third score: ";
    std::cin >> score3;

    if (!(score1 >= 0 && score1 <= 100 && score2 >= 0 && score2 <= 100 && score3 >= 0 && score3 <= 100)) {
        std::cout << "Inputs are invalid." << std::endl;
        return 1;
    }

    const double avg = (score1 + score2 + score3) / 3.;

    char grade = 'F';
    if (avg > 90) {
        grade = 'A';
    }
    else if (avg >= 80 && avg < 90) {
        grade = score3 >= 90 ? 'A' : 'B';
    }
    else if (avg >= 70 && avg < 80) {
        grade = score3 >= 80 ? 'B' : 'C';
    }
    else if (avg >= 60 && avg < 70) {
        grade = score3 >= 70 ? 'C' : 'D';
    }
    else if (score3 >= 60) {
        grade = 'D';
    }

    std::cout << grade << std::endl;
    
    return 0;
}
```
