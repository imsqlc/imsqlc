н
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
    
Хорошо, вот обновленная версия программы на C++, которая выводит информацию о магазинах заданной направленности, номеру магазина и номеру телефона:

```c++
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

struct Shop {
    string direction;
    int number;
    string address;
    string phone;
};

bool compareDirections(Shop shop, string direction) {
    return shop.direction == direction;
}

bool compareNumber(Shop shop, int number) {
    return shop.number == number;
}

bool comparePhone(Shop shop, string phone) {
    return shop.phone == phone;
}

int main() {
    vector<Shop> allShops = {
        {"автомагазин", 1, "ул. Ленина, 10", "+7 (999) 123-45-67"},
        {"аптека", 2, "ул. Пушкина, 15", "+7 (999) 765-43-21"},
        {"мебельный", 3, "ул. Гагарина, 20", "+7 (999) 111-22-33"}
    };

    // Запросы по направленности магазина
    string direction;
    cout << "Введите направленность магазина: ";
    cin >> direction;
    cout << endl;

    vector<Shop> filteredDirection;
    copy_if(allShops.begin(), allShops.end(), back_inserter(filteredDirection), [direction](Shop shop) { return compareDirections(shop, direction); });

    for (auto shop : filteredDirection) {
        cout << "Магазин #" << shop.number << endl;
        cout << "Направленность: " << shop.direction << endl;
        cout << "Адрес: " << shop.address << endl;
        cout << "Телефон: " << shop.phone << endl << endl;
    }

    // Запрос по номеру магазина
    int shopNumber;
    cout << "Введите номер магазина: ";
    cin >> shopNumber;
    cout << endl;

    vector<Shop> filteredShopNumber;
    copy_if(allShops.begin(), allShops.end(), back_inserter(filteredShopNumber), [shopNumber](Shop shop) { return compareNumber(shop, shopNumber); });

    if (filteredShopNumber.size() == 1) {
        Shop shop = filteredShopNumber[0];

        cout << "Магазин #" << shop.number << endl;
        cout << "Направленность: " << shop.direction << endl;
        cout << "Адрес: " << shop.address << endl;
        cout << "Телефон: " << shop.phone << endl << endl;
    } else {
        cout << "Магазин не найден" << endl << endl;
    }

    // Запрос по номеру телефона
    string phone;
    cout << "Введите номер телефона магазина: ";
    cin >> phone;
    cout << endl;

    vector<Shop> filteredPhone;
    copy_if(allShops.begin(), allShops.end(), back_inserter(filteredPhone), [phone](Shop shop) { return comparePhone(shop, phone); });

    if (filteredPhone.size() == 1) {
        Shop shop = filteredPhone[0];

        cout << "Магазин #" << shop.number << endl;
        cout << "Направленность: " << shop.direction << endl;
        cout << "Адрес: " << shop.address << endl;
        cout << "Телефон: " << shop.phone << endl << endl;
    } else {
        cout << "Магазин не найден" << endl << endl;
    }

    return 0;
}
```

В этой версии программы добавлены функции сравнения соответствующих полей структуры `Shop`. Затем для каждого типа запроса вызывается функция `copy_if()`, которая создает новый вектор, содержащий только элементы, удовлетворяющие требованию запроса. Если количество элементов равно 1, то выводится информация о магазине. Если количество элементов равно 0, то выводится сообщение "Магазин не найден".



Это можно сделать, добавив строку #include <locale> и вызывая функции setlocale в начале main ():

c++
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
#include <locale>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    vector<string> words = {"мороженое", "молоко", "сыр", "кефир"};

    string input;
    cout << "Введите слово: ";
    cin >> input;

    if (find(words.begin(), words.end(), input) != words.end()) {
        cout << "Слово найдено!" << endl;
    } else {
        cout << "Слово не найдено!" << endl;
    }

    return 0;
}
