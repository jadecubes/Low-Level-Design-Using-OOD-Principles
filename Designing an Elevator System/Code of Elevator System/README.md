# Code of Elevator System
We’ve discussed different aspects of the elevator system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the elevator system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the elevator control system:

- Java

- C#

- Python

- C++

JavaScript

## Elevator system classes
In this section, we’ll provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we aren’t defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public methods function.
```

### Enumerations
First of all, we will define all the enumerations required in the elevator system. According to the class diagram, there are three enumerations used in the system i.e., ElevatorState, Direction and DoorState. The code to implement these enumerations is as follows:

```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```
```java
// definition of enumerations used in elevator system
enum ElevatorState {
	IDLE,
    UP,
    DOWN
}

enum Direction {
    UP, 
    DOWN
}

enum DoorState {
	OPEN,
    CLOSE
}
       Enum definitions
```

```c#
// definition of enumerations used in elevator system
enum ElevatorState {
	IDLE,
    UP,
    DOWN
}

enum Direction {
    UP, 
    DOWN
}

enum DoorState {
	OPEN,
    CLOSE
}
      Enum definitions
```

```python
# definition of enumerations used in elevator system
class ElevatorState(enum.Enum):
	IDLE = 1
	UP = 2
	DOWN = 3

class Direction(enum.Enum):
    UP = 1
	DOWN = 2


class DoorState(enum.Enum):
	OPEN = 1
	CLOSE = 2
  
                  Enum definitions
```

```c++
// definition of enumerations used in elevator system
enum ElevatorState {
	IDLE,
    UP,
    DOWN
};

enum Direction {
    UP, 
    DOWN
};

enum DoorState {
	OPEN,
    CLOSE
};
                Enum definitions
```

```javascript
// definition of enumerations used in elevator system
const ElevatorState = Object.freeze({
	IDLE,
    UP,
    DOWN
});
const Direction = Object.freeze({
    UP, 
    DOWN
});
const DoorState = Object.freeze({
	OPEN,
    CLOSE
});
            Enum definitions
```
### Button
This section contains the implementation of a Button class and its subclasses which are HallButton and the ElevatorButton. The Button class has a pure virtual function isPressed() in it. The code to implement this relationship is given below:
```java
public abstract class Button {
    private boolean status;

    public pressDown();
    public abstract boolean isPressed();
}

public class HallButton extends Button  {
    private Direction buttonSign;

    public boolean isPressed() {
        // definition
    }
}

public class ElevatorButton extends Button  {
    private int destinationFloorNumber;

    public boolean isPressed() {
        // definition
    }
}
         Button and its subclasses
```

```c#
public abstract class Button {
    private bool status;

    public PressDown();
    public abstract boolean IsPressed();
}

class HallButton : Button  {
    private Direction buttonSign;

    public override bool IsPressed() {
        // definition
    }
}

class ElevatorButton : Button  {
    private int destinationFloorNumber;

    public override bool IsPressed() {
        // definition
    }
}
           Button and its subclasses
```

```python
from abc import ABC, abstractmethod
class Button(ABC):
    def __init__(self, status):
        self.__status = status

    def press_down():
        None

    @abstractmethod
    def is_pressed(self):
        pass

class HallButton(Button):
    def __init__(self, button_sign):
        self.__button_sign = button_sign

    def is_pressed(self):
        pass

class ElevatorButton(Button):
    def __init__(self, destination_floor_number):
        self.__destination_floor_number = destination_floor_number

    def is_pressed(self):
        pass
        
         Button and its subclasses
```

```c++
class Button {
    private: 
        bool status;

    public: 
        void pressDown();
        virtual bool isPressed() = 0;
};

class HallButton : public Button  {
    private: 
        Direction buttonSign;

    public: 
        bool isPressed() {
            // definition
        }
};

class ElevatorButton : public Button  {
    private: 
        int destinationFloorNumber;

    public: 
        bool isPressed() {
            // definition
        }
};
         Button and its subclasses
```

```javascript
class Button {
    #status
    constructor(status = null) {
        if (this.constructor == Button) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else {
          this.#status = status;
        }
    }
    pressDown();
    isPressed();
}

class HallButton extends Button  {
    #buttonSign;
    constructor(status, buttonSign) {
        this.#buttonSign = buttonSign;
        super(status);
    }
    isPressed() {
        // definition
    }
}

class ElevatorButton extends Button  {
    #destinationFloorNumber;
    constructor(status, destinationFloorNumber) {
        this.#destinationFloorNumber = destinationFloorNumber;
        super(status);
    }
    isPressed() {
        // definition
    }
}
          Button and its subclasses
```

### Elevator panel and hall panel
### Display
### Elevator car
### Door and floor
### Elevator system and building
## Wrapping up
