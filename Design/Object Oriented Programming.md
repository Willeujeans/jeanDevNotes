# Object Oriented Programming
## Abstraction
_what does the object do rather than how does the object do it_
For example you can create a `Car` class that has a `start()` and `stop()` method. You do not need to know that the `stop()` method:  
presses the breaks -> activating the calipers -> pushing the plates onto the wheels of the car slowing it to a stop.  
In actual code abstraction is often implemented using interfaces and abstract classes.  
This leads to highly modular designs because you can apply these general methods to multiple different things. Such as having an `abstract Class` called `Vehicle` which contains the `start()` and `stop()` methods which applies to cars, trains, scooters, ect.  

# Aggregation
_This is an Object that has another Object. A Library contains many books, but the books can exist without the library._

``` Python
class Book:
    def __init__(self, title):
        self.title = title

    def get_title(self):
        return self.title


class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)
```

## Association
_Represents the relationships between objects_
- One to One
- One to Many
- Many to One, and
- Many to Many
Association can be unidirectional or bidirectional

---

### Example
- One country can have one Prime Minister (one to one)
- The Prime Minister can have many ministers (one to many)
- MP's can have one prime minister (many to one)
- Ministers can have many departments (many to many)

---

## Cohesion
_This speaks to the idea of a component performing a single task, a class should be one type of thing, and its methods should do one thing_

---

## Composition
_Its a 'has-a' relationship where one Object will contain another Object that are not meant to exist outside its container._

Such as a `Car` containing an `Engine`, however the engine is not useful outside of a machine that is using it. If you were to _delete_ the `Engine` the `Car` would still exist, if you _delete_ the `Car` the `Engine` also gets deleted.

``` python
class Engine:
	def __init__(self, horsepower):
		self.horsepower = horsepower

class Car:
	def __init__(self, horsepower):
		Engine self.engine = Engine(horsepower)
```

## Coupling
_When Classes know private details about each other it means they are dependent upon each other, making them coupled_
## Encapsulation
Containing data and functionality within a defined boundary
This is normally achieved through the creation of `classes` with `private` elements within them
## Getters and Setters
If a `Class's` variables are `private` that means other `Entities` cannot modify them, it also means they cannot access them directly. Which is why we provide methods that handle the specifics of that access.
- Getters: return the variable
- Setters: set the variable's value
## Inheritance
All `Animal`s have a `name` and can `walk()` but each of those look a little different, having a `Pig` inherit from the `Animal` class means we don't have to add all of those basics in, so we don't need to give every animal its own written variable in its class

Subclass (Child)
Superclass (Parent)
## Interface
Defines a contract that classes must implement
used for polymorphism and decoupling components

Populating the interface with methods will require all classes that extend from the interface to have a version of that method implemented
## Polymorphism
Uses inherited methods to perform different tasks allowing us to perform a single action in different ways.