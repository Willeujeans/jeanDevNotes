# Design Patterns
_Principles followed in organizing code and how objects interact with each other._
- **Architectural Patterns:** universal and high-level patterns that can be used for whole applications.  
- **Idioms:** basic and low-level patterns, can be specific to languages.
# Creational Design Patterns
_Patterns that involve the creation of Objects._
## Factory
_A class handles the creation of Objects._
A Factory class handles the creation of Objects (_products_).
### Example
``` python
class Burger:
    def __init__(self, ingredients):
        self.ingredients = ingredients
    
    def describe(self):
        print(self.ingredients)


class BurgerFactory:
    def createCheeseBurger(self):
        ingredients = ["bun", "cheese", "meat"]

    def createVeganBurger(self):
        ingredients = ["bun", "cheese", "tofu"]

    def createBurger(self):
        ingredients = ["bun", "tomato", "meat"]

burgerFactoryInstance = BurgerFactory()
burgerFactoryInstance.createCheeseBurger().describe()
```

---  
## Abstract Factory
_An interface that handles the creation of classes that will create Objects._
You create a Factory interface that other concrete factories will implement.

---  
## Builder
_creates an Object one piece at a time_
Director will select a builder class that implements the builder interface, the concrete builders will then have their methods invoked creating the product.
``` python
class Burger:
	def __init__(self):
		self.buns = None
		self.meat = None
		self.cheese = None
		
	def set_buns(self, bun_style):
		self.buns = bunstyle
		
	def set_meat(self, meat_style):
		self.meat = meat_style
		
	def set_cheese(self, cheese_style):
		self.cheese = cheese_style


class BurgerBuilder:
	def __init__(self):
		self.burger = Burger()
		
	def add_buns(self, bun_style):
		self.burger.set_buns(bun_style)
		return self
		
	def add_meat(self, meat_style):
		self.burger.set_meat(meat_style)
		return self
		
	def add_cheese(self, cheese_style):
		self.burger.set_cheese(cheese_style)
		return self

burger = BurgerBuilder()
			.add_buns("sesame")
			.add_meat("tofu")
			.add_cheese("swiss")
			.build()
```

--- 
## Prototype
_Copies existing objects without making the code dependent on their classes._

---  
## Singleton
_A singular class instance with global access._

---  
# Structural Patterns
_Explain how to assemble objects and classes into larger structures, while keeping structures flexible and efficient._

---  
# Behavioral Patterns
_Take care of effective communication and the assignment of responsibilities between objects._
