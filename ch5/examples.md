## 챕터5

> 📅 **날짜:** 11/01  
> 📖 **페이지:** 169~210p

### 계단 패턴 출력

```c++
#include <iomanip>
#include <iostream>
#include <string>

int main() {
    short type;
    short size;
    do {
        std::cout << "Enter pattern type (1~4): ";
        std::cin >> type;
    } while (type < 1 || type > 4);
    do {
        std::cout << "Enter size (1~9): ";
        std::cin >> size;
    } while (type < 1 || type > 9);

    switch (type) {
        case 1: {
            for (int i = 1; i <= size; i++) {
                std::cout << std::string(i, '*') << std::endl;
            }
            break;
        }
        case 2:
        case 3: {
            for (int i = size; i >= 1; i--) {
                std::cout << std::setw(size) << std::string(i, '*') << std::endl;
            }
            break;
        }
        case 4: {
            for (int i = 1; i <= size; i++) {
                std::cout << std::setw(size) << std::string(i, '*') << std::endl;
            }
            break;
        }
        default:
            return 1;
    }

    return 0;
}
```

### 피라미드 패턴 출력

```c++
#include <iomanip>
#include <iostream>
#include <string>

int main() {
    short type;
    short size;
    do {
        std::cout << "Enter pattern type (1~2): ";
        std::cin >> type;
    } while (type < 1 || type > 2);
    do {
        std::cout << "Enter size: ";
        std::cin >> size;
    } while (size < 1);

    const int maxCount = size * 2 - 1;
    if (type == 1) {
        for (int i = size; i >= 1; i--) {
            const int starCount = i * 2 - 1;
            const int spaceCount = (maxCount - starCount) / 2;
            std::cout << std::string(spaceCount, ' ') << std::string(starCount, '*') << std::endl;
        }
    } else if (type == 2) {
        for (int i = 1; i <= size; i++) {
            const int starCount = i * 2 - 1;
            const int spaceCount = (maxCount - starCount) / 2;
            std::cout << std::string(spaceCount, ' ') << std::string(starCount, '*') << std::endl;
        }
    }

    return 0;
}
```

### 범위 내에서 홀수 짝수 출력

```c++
#include <iostream>

int main() {
    int min, max;
    do {
        std::cout << "Enter min positive number: ";
        std::cin >> min;
    } while (min < 1);
    do {
        std::cout << "Enter max positive number: ";
        std::cin >> max;
    } while (max < min);

    const int minEven = min % 2 == 0 ? min : min + 1;
    const int minOdd = min % 2 == 1 ? min : min + 1;

    std::cout << "odd = ";
    for (int i = minOdd; i <= max; i += 2) {
        std::cout << i << ' ';
    }
    std::cout << std::endl;
    std::cout << "even = ";
    for (int i = minEven; i <= max; i += 2) {
        std::cout << i << ' ';
    }
    std::cout << std::endl;

    return 0;
}
```

### 범위 내에서 5와 7로 나누어 떨어지는 숫자 출력

```c++
#include <iostream>

int main() {
    const int base = 5 * 7;
    for (int factor = 1; base * factor <= 100; factor++) {
        std::cout << base * factor << ' ';
    }
    std::cout << std::endl;

    return 0;
}
```
