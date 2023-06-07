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


Ой, я снова что-то упустил. Извините за это. Вот полный код, который включает в себя классы "Shop" и "Supermarket", а также функцию main, которая использует объекты классов для фильтрации и отображения информации о магазинах и супермаркетах:

#include <iostream>
#include <vector>
#include <algorithm>
#include <string>

using namespace std;

class Shop {
private:
    string direction;
    int number;
    string address;
    string phone;
public:
    Shop(string dir, int num, string addr, string ph) {
        direction = dir;
        number = num;
        address = addr;
        phone = ph;
    }

    Shop() {
        direction = "";
        number = 0;
        address = "";
        phone = "";
    }

    ~Shop() {}

    string getDirection() const {
        return direction;
    }

    int getNumber() const {
        return number;
    }

    string getAddress() const {
        return address;
    }

    string getPhone() const {
        return phone;
    }

    bool operator==(const Shop& other) const {
        return (direction == other.direction && number == other.number && address == other.address && phone == other.phone);
    }
};

class Supermarket : public Shop {
private:
    int cash_registers;
    int employees;
public:
    Supermarket(string dir, int num, string addr, string ph, int cr, int emp) : Shop(dir, num, addr, ph) {
        cash_registers = cr;
        employees = emp;
    }

    Supermarket() {
        cash_registers = 0;
        employees = 0;
    }

    ~Supermarket() {}

    int getCashRegisters() const {
        return cash_registers;
    }

    int getEmployees() const {
        return employees;
    }
};

int main() {
    vector<Shop> shops;
    shops.push_back(Shop("North", 1, "123 Main St", "555-1234"));
    shops.push_back(Shop("South", 2, "456 Elm St", "555-5678"));
    shops.push_back(Shop("East", 3, "789 Oak St", "555-9012"));
    shops.push_back(Supermarket("West", 4, "321 Pine St", "555-3456", 10, 50));

    cout << "All shops:" << endl;
    for (const auto& shop : shops) {
        cout << shop.getDirection() << " " << shop.getNumber() << " " << shop.getAddress() << " " << shop.getPhone() << endl;
    }

    vector<Supermarket> supermarkets;
    for (const auto& shop : shops) {
        if (auto* supermarket = dynamic_cast<const Supermarket*>(&shop)) {
            supermarkets.push_back(*supermarket);
        }
    }

    cout << "Supermarkets only:" << endl;
    for (const auto& supermarket : supermarkets) {
        cout << supermarket.getDirection() << " " << supermarket.getNumber() << " " << supermarket.getAddress() << " " << supermarket.getPhone() << " " << supermarket.getCashRegisters() << " " << supermarket.getEmployees() << endl;
    }

    return 0;
}


Если у вас есть какие-либо вопросы по этому коду, я буду рад ответить на них.