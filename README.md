no jн
 👋 Hi
 
---

🔖 My certificates: <p><a href="https://coursera.org/share/641266f14fe2f0ea3710282483673a0c">☁ Introduction to HTML5</a></p> </p>
<p><a href="https://www.coursera.org/account/accomplishments/verify/S3KBB54TCNXJ">☁ Introduction to CSS in Web Development</a></p> </p>
<p><a href="https://www.coursera.org/account/accomplishments/verify/C4M3GL3TLAVC">☁ Introduction to Javascript: The Basics</a></p> </p>
<p><a href="https://www.coursera.org/account/accomplishments/verify/465U9W88MDVT">☁ 
Introduction to Web Development</a></p> </p>
<p><a href="https://www.coursera.org/account/accomplishments/certificate/UR7EYABXDK7U">☁ 
Build a Twitter Clone Front-End with ReactJS</a></p> </p>
<p><a href="https://www.coursera.org/account/accomplishments/verify/8P2JR5YY3C2A">☁ 
HTML, CSS, and Javascript for Web Developers</a></p> </p>
<p><a href="https://www.coursera.org/account/accomplishments/verify/6YJS3J9FTB49">☁ Programming Foundations with JavaScript, HTML and CSS</a></p> </p>

---

👨🏻‍💻 How to contact me: <p><a href="https://t.me/devuejs">💬Telegram</a></p>
    
Пример реализации класса с деструктором и несколькими конструкторами:

```c++
#include <iostream>
using namespace std;

class MyClass {
private:
    int* data;
public:
    MyClass() {  // конструктор по умолчанию
        cout << "Вызван конструктор по умолчанию" << endl;
        data = new int[10];
    }
    MyClass(int size) {  // конструктор с параметром
        cout << "Вызван конструктор с параметром" << endl;
        data = new int[size];
    }
    ~MyClass() {  // деструктор
        cout << "Вызван деструктор" << endl;
        delete[] data;
    }
};

int main() {
    MyClass mc1;  // вызывается конструктор по умолчанию
    MyClass mc2(20);  // вызывается конструктор с параметром
    return 0;
}
```

Конструктор по умолчанию вызывается при создании объекта без параметров. В данном примере, вызов `MyClass mc1` без параметров вызывает конструктор по умолчанию.

Конструктор с параметром вызывается с аргументами. В данном примере, вызов `MyClass mc2(20);` создает объект `mc2` с массивом из 20 элементов.

Деструктор вызывается, когда объект теряет свое существование. В данном примере, если объект `mc2` выйдет за пределы блока `main()`, он будет уничтожен с помощью деструктора.

Примеры реализации класса `Shop` с использованием деструктора и нескольких конструкторов:

```c++
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
#include <locale>

using namespace std;

class Shop {
private:
    string direction;
    int number;
    string address;
    string phone;
public:
    Shop() {
        direction = "";
        number = 0;
        address = "";
        phone = "";
        cout << "Вызван конструктор по умолчанию" << endl;
    }

    Shop(string d, int n, string a, string p) {
        direction = d;
        number = n;
        address = a;
        phone = p;
        cout << "Вызван конструктор с параметрами" << endl;
    }

    Shop(const Shop& other) {
        direction = other.direction;
        number = other.number;
        address = other.address;
        phone = other.phone;
        cout << "Вызван конструктор копирования" << endl;
    }

    ~Shop() {
        cout << "Вызван деструктор" << endl;
    }

    bool compareDirections(string direction) {
        return this->direction == direction;
    }

    bool compareNumber(int number) {
        return this->number == number;
    }

    bool comparePhone(string phone) {
        return this->phone == phone;
    }

    string getDirection() {
        return direction;
    }

    int getNumber() {
        return number;
    }

    string getAddress() {
        return address;
    }

    string getPhone() {
        return phone;
    }
};

int main() {
    setlocale(LC_ALL, "Russian");

    vector<Shop> allShops = {
        Shop("автомагазин", 1, "ул. Ленина, 10", "+7 (999) 123-45-67"),
        Shop("аптека", 2, "ул. Пушкина, 15", "+7 (999) 765-43-21"),
        Shop("мебельный", 3, "ул. Гагарина, 20", "+7 (999) 111-22-33")
    };

    Shop defaultShop; // Вызывается конструктор по умолчанию

    // Вызывается конструктор копирования
    Shop copiedShop(allShops[0]);

    // Вызывается конструктор с параметрами
    Shop newShop("рыбный", 4, "ул. Рыбная, 5", "+7 (999) 222-33-44");

    // Вызывается деструктор
    copiedShop = defaultShop;

    return 0;
}
``` 

В этом примере мы добавили три конструктора: конструктор по умолчанию (`Shop()`), конструктор с параметрами (`Shop(string d, int n, string a, string p)`) и конструктор копирования (`Shop(const Shop& other)`).

Конструктор по умолчанию задает значения членов класса по умолчанию, а конструктор с параметрами инициализирует их переданными значениями.

Конструктор копирования создает новый объект, который является копией объекта-аргумента. Он назначает значения членов класса объекта-аргумента членам класса нового объекта.

Деструктор освобождает память, занятую объектами класса, перед тем как они удаляются.

Как видно из код