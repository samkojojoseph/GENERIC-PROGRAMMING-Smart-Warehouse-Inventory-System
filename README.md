from typing import Generic, TypeVar

# Create a generic type
T = TypeVar('T')


# Generic Storage class
class Storage(Generic[T]):

    def __init__(self):
        self.item = None

    # Store an item
    def store(self, item: T):
        self.item = item

    # Retrieve the stored item
    def retrieve(self) -> T:
        return self.item


# --------------------------------
# Demonstration
# --------------------------------

# 1. Using an integer
integer_storage = Storage[int]()
integer_storage.store(100)

print("Integer:")
print(integer_storage.retrieve())


# 2. Using a string
string_storage = Storage[str]()
string_storage.store("Smart Warehouse")

print("\nString:")
print(string_storage.retrieve())


# 3. Using a list
list_storage = Storage[list]()
list_storage.store(["Laptop", "Keyboard", "Mouse"])

print("\nList:")
print(list_storage.retrieve())
