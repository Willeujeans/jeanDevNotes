# Dependency Injection
_A Design pattern where object’s dependencies are provided by an external source._
## Dependencies
_Objects that a class needs to function._
A Car depends on an Engine, therefore engine is a dependency.
## Injectors
Frameworks or containers that manage the creation and giving of dependencies to classes that need them.  
- **Constructor Injection:** Dependencies are provided through the class constructor.
- **Setter Injection:** Dependencies are provided via setter methods.
- **Interface Injection:** The dependency provides an injector method that will inject the dependency into any client that passes itself to the method.

``` Python
# Base Engine class
class Engine:
    def start(self):
        raise NotImplementedError("Subclasses must implement this method.")

# GasEngine class inheriting from Engine
class GasEngine(Engine):
    def start(self):
        return "Gas engine started."

# ElectricEngine class inheriting from Engine
class ElectricEngine(Engine):
    def start(self):
        return "Electric engine started silently."

# Car class
class Car:
    def __init__(self, engine: Engine):
        self.engine = engine

    def start(self):
        return self.engine.start()

# CarFactory class
class CarFactory:
    def create_car(self, engine_type):
        if engine_type == "gas":
            return Car(GasEngine())
        elif engine_type == "electric":
            return Car(ElectricEngine())
        else:
            raise ValueError("Unknown engine type")

# Main execution
if __name__ == "__main__":
    factory = CarFactory()

    # Create a gas-powered car
    gas_car = factory.create_car("gas")
    print(gas_car.start())  # Output: Gas engine started.

    # Create an electric car
    electric_car = factory.create_car("electric")
    print(electric_car.start())  # Output: Electric engine started silently.
```