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
    
Пример реализации класса `Shop` с использованием деструктора и нескольких конструкторов:

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
    Shop() : direction(""), number(0), address(""), phone("") {
        // конструктор по умолчанию
    }

    Shop(const string& d, int n, const string& a, const string& p) : direction(d), number(n), address(a), phone(p) {
        // конструктор с параметрами
    }

    ~Shop() {
        // деструктор
    }

    bool compareDirections(const string& direction) const {
        return this->direction == direction;
    }

    bool compareNumber(int number) const {
        return this->number == number;
    }

    bool comparePhone(const string& phone) const {
        return this->phone == phone;
    }

    const string& getDirection() const {
        return direction;
    }

    int getNumber() const {
        return number;
    }

    const string& getAddress() const {
        return address;
    }

    const string& getPhone() const {
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

    // Запросы по направленности магазина
    string direction;
    cout << "Введите направленность магазина: ";
    cin >> direction;
    cout << endl;

    vector<Shop> filteredDirection;
    copy_if(allShops.begin(), allShops.end(), back_inserter(filteredDirection), [direction](Shop shop) { return shop.compareDirections(direction); });

    for (auto shop : filteredDirection) {
        cout << "Магазин #" << shop.getNumber() << endl;
        cout << "Направленность: " << shop.getDirection() << endl;
        cout << "Адрес: " << shop.getAddress() << endl;
        cout << "Телефон: " << shop.getPhone() << endl << endl;
    }

    // Запрос по номеру магазина
    int shopNumber;
    cout << "Введите номер магазина: ";
    cin >> shopNumber;
    cout << endl;

    vector<Shop> filteredShopNumber;
    copy_if(allShops.begin(), allShops.end(), back_inserter(filteredShopNumber), [shopNumber](Shop shop) { return shop.compareNumber(shopNumber); });

    if (filteredShopNumber.size() == 1) {
        Shop shop = filteredShopNumber[0];

        cout << "Магазин #" << shop.getNumber() << endl;
        cout << "Направленность: " << shop.getDirection() << endl;
        cout << "Адрес: " << shop.getAddress() << endl;
        cout << "Телефон: " << shop.getPhone() << endl << endl;
    } else {
        cout << "Магазин не найден" << endl << endl;
    }

    // Запрос по номеру телефона
    string phone;
    cout << "Введите номер телефона магазина: ";
    cin >> phone;
    cout << endl;

    vector<Shop> filteredPhone;
    copy_if(allShops.begin(), allShops.end(), back_inserter(filteredPhone), [phone](Shop shop) { return shop.comparePhone(phone); });

    if (filteredPhone.size() == 1) {
        Shop shop = filteredPhone[0];

        cout << "Магазин #" << shop.getNumber() << endl;
        cout << "Направленность: " << shop.getDirection() << endl;
        cout << "Адрес: " << shop.getAddress() << endl;
        cout << "Телефон: " << shop.getPhone() << endl << endl;
    } else {
        cout << "Магазин не найден" << endl << endl;
    }

    return 0;
}
```

Здесь мы добавили конструктор по умолчанию `Shop()`, конструктор с параметрами `Shop(const string& d, int n, const string& a, const string& p)` и деструктор Шоп `~Shop()`. В остальном код остался неизменным.