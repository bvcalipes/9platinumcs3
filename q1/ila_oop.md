# ILA 3-1: Applying the Four Pillars of OOP
**Name:** Bashaier V. Calipes
**Section:** Platinum
**Date:** August 20, 2026

## Sari-Sari Store Inventory

### 1. Encapsulation
Encapsulation bundles the product details—such as `product_name`, `price`, and `stock`—along with the functions that operate on them inside a single `Product` class. Private attributes prevent direct, unauthorized modifications from external parts of the program. Instead, controlled updates occur through explicit methods like `restock(amount)` or `sell(quantity)`, ensuring that stock levels never accidentally drop below zero.

```python
class Product:
    def __init__(self, name, price, stock):
        self.name = namej
        self.price = price
        self.__stock = stock  # Private attribute

    def sell(self, quantity):
        if quantity <= self.__stock:
            self.__stock -= quantity
            return True
        return False
```

### 2. Abstract
Abstraction hides complex background processing and exposes only simple, necessary operations to the user or cashier interface. Instead of requiring the main program to manually track total earnings, update stock, and calculate remaining inventories line by line, it simply calls a clear method like process_sale(). This simplifies the overall system design and reduces code complexity.
```python
class StoreInventory:
    def process_sale(self, product, quantity):
        if product.sell(quantity):
            print("Sale completed successfully.")
        else:
            print("Error: Out of stock.")
```

### 3. Inheritance
Inheritance is an object-oriented-programming mechanism that lets a new class adopt the properties and methods of an existing class. It helps programmers reuse code, build class hierarchies, and add or change features without rewriting old logic.

```python
class PerishableProduct(Product):
    def __init__(self, name, price, stock, expiration_date):
        super().__init__(name, price, stock)
        self.expiration_date = expiration_date
```

### 4. Polymorphism
Polymorphism allows different objects to perform the exact same action in their own customized ways. For example, a single calculate_total() command can automatically figure out standard pricing for regular goods while applying discounts for promo items.

```python
class DiscountedProduct(Product):
    def __init__(self, name, price, stock, discount_rate):
        super().__init__(name, price, stock)
        self.discount_rate = discount_rate

    def calculate_total(self, quantity):
        return (self.price * quantity) * (1 - self.discount_rate)
```
## Reflection
Among the four pillars, Encapsulation would be the most useful in improving the sari-sari store inventory system. In a store setting, maintaining accurate inventory counts and preventing invalid date entry (like negative stock or accidental price overrides) is critical. Encapsulation secures sensitive product data by restricting direct access and forcing all updates to pass through validated class methods, ensuring data integrity across the entire application.