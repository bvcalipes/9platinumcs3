# ILA 3-1: Applying the Four Pillars of OOP
**Name:** Bashaier V. Calipes
**Section:** Platinum

## Sari-Sari Store Inventory
### 1. Encapsulation
Encapsulation bundles the product details—such as `product_name`, `price`, and `stock`—along with the functions that operate on them inside a single `Product` class. Private attributes prevent direct, unauthorized modifications from external parts of the program. Instead, controlled updates occur through explicit methods like `restock(amount)` or `sell(quantity)`, ensuring that stock levels never accidentally drop below zero.

```python
class Product:
    def __init__(self, name, price, stock):
        self.name = name
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