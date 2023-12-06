#include <iostream>
#include <vector>
class Product {
public:
    std::string name;
    std::string manufacturer;
    double price;
    int storagePeriod;
    int quantity;
    Product(std::string n, std::string m, double p, int sp, int q)
        : name(n), manufacturer(m), price(p), storagePeriod(sp), quantity(q) {}
};
int main() {
    // Створення вектору об'єктів
    std::vector<Product> products = {
        {"Продукт1", "Виробник 1", 10.5, 30, 50},
        {"Продукт2", "«Виробник 2", 15.2, 45, 25},
        // Додайте інші об'єкти за необхідністю
    };
    // а) перелік товарів для заданого найменування
    std::string desiredName = "Продукт 1";
    std::cout << "Товари з назвою '" << desiredName << "':\n";
    for (const auto& product : products) {
        if (product.name == desiredName) {
            std::cout << product.name << ", " << product.manufacturer << ", " << product.price
                      << ", " << product.storagePeriod << ", " << product.quantity << "\n";
        }
    }
    // б) перелік товарів для заданого найменування, вартість яких не перевищує зазначеної
    double maxPrice = 12.0;
    std::cout << "\nТовари з назвою '" << desiredName << "' and price not exceeding " << maxPrice << ":\n";
    for (const auto& product : products) {
        if (product.name == desiredName && product.price <= maxPrice) {
            std::cout << product.name << ", " << product.manufacturer << ", " << product.price
                      << ", " << product.storagePeriod << ", " << product.quantity << "\n";
        }
    }
    // в) список товарів, термін зберігання яких більший за заданий
    int desiredStoragePeriod = 40;
    std::cout << "\nПродукти з терміном зберігання більше " << desiredStoragePeriod << ":\n";
    for (const auto& product : products) {
        if (product.storagePeriod > desiredStoragePeriod) {
            std::cout << product.name << ", " << product.manufacturer << ", " << product.price
                      << ", " << product.storagePeriod << ", " << product.quantity << "\n";
        }
    }
    return 0;
}
