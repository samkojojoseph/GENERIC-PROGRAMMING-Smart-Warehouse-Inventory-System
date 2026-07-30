from typing import Generic, TypeVar

T = TypeVar("T")


class Inventory(Generic[T]):
    def __init__(self, item_type):
        self.item_type = item_type
        self.items = []

    def add_item(self, item: T):

        if not isinstance(item, self.item_type):
            raise TypeError(
                f"Invalid type. Expected {self.item_type.__name__}, "
                f"but got {type(item).__name__}"
            )

        self.items.append(item)

    def get_items(self):
        return self.items

    def display_items(self):
        print("Type:", self.item_type.__name__)
        print("Items:", self.items)


# String inventory
products = Inventory[str](str)

products.add_item("Laptop")
products.add_item("Phone")
products.add_item("Tablet")

products.display_items()

print()

# Integer inventory
stock = Inventory[int](int)

stock.add_item(10)
stock.add_item(20)
stock.add_item(30)

stock.display_items()

print()

# Float inventory
prices = Inventory[float](float)

prices.add_item(500.50)
prices.add_item(1000.75)

prices.display_items()

print()

# List inventory
serial_numbers = Inventory[list](list)

serial_numbers.add_item(["SN001", "SN002"])
serial_numbers.add_item(["SN003", "SN004"])

serial_numbers.display_items()
