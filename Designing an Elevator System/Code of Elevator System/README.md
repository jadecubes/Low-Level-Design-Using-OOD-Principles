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
ElevatorPanel and the HallPanel are classes which use the instance of ElevatorButton and HallButton respectively. The code to implement these classes is provided below:
```java
public class ElevatorPanel {
    private List<ElevatorButton> floorButtons;
    private ElevatorButton openButton;
    private ElevatorButton closeButton;
}

public class HallPanel {
    private HallButton up;
    private HallButton down;
}
 
           The ElevatorPanel and HallPanel classes
```

```c#
class ElevatorPanel {
    private List<ElevatorButton> floorButtons;
    private ElevatorButton openButton;
    private ElevatorButton closeButton;
}

class HallPanel {
    private HallButton up;
    private HallButton down;
}
      The ElevatorPanel and HallPanel classes
```

```python
class ElevatorPanel:
    def __init__(self, floor_buttons, open_button, close_button):
        self.__floor_buttons = floor_buttons
        self.__open_button = open_button
        self.__close_button = close_button


class HallPanel:
    def __init__(self, up, down):
        self.__up = up
        self.__down = down
	
	The ElevatorPanel and HallPanel classes
```

```c++
class ElevatorPanel {
    private: 
        vector<ElevatorButton> floorButtons;
        ElevatorButton openButton;
        ElevatorButton closeButton;
};

class HallPanel {
    private: 
        HallButton up;
        HallButton down;
};
 
            The ElevatorPanel and HallPanel classes
```

```javascript
class ElevatorPanel {
    #floorButtons;
    #openButton;
    #closeButton;
    constructor(openButton, closeButton) {
        this.#openButton = openButton;
        this.#closeButton = closeButton;
        this.#floorButtons = new Array();
    }
}

class HallPanel {
    #up;
    #down;
    constructor(up, down) {
        this.#up = up;
        this.#down = down;
    }
}
       The ElevatorPanel and HallPanel classes
```

### Display
This component shows the implementation of the Display class. This class is responsible for showing the display inside and outside of the elevator cars. The code to implement this class is shown below:

```java
public class Display {
    private int floor;
    private int capacity;
    private Direction direction;

    public void showElevatorDisplay();
    public void showHallDisplay();
}
   The Display class
```

```c#
class Display {
    private int floor;
    private int capacity;
    private Direction direction;

    public void showElevatorDisplay();
    public void showHallDisplay();
}
           The Display class
```

```python
class Display:
    def __init__(self, floor, capacity, direction):
        self.__floor = floor
        self.__capacity = capacity
        self.__direction = direction

    def show_elevator_display():
        None

    def show_hall_display():
        None
	
       The Display class
```

```c++
class Display {
    private: 
        int floor;
        int capacity;
        Direction direction;

    public: 
        void showElevatorDisplay();
        void showHallDisplay();
};
      The Display class
```

```javascript
class Display {
    #floor;
    #capacity;
    #direction;

    constructor(floor, capacity, direction) {
        this.#floor = floor;
        this.#capacity = capacity;
        this.#direction = direction;
    }

    showElevatorDisplay();
    showHallDisplay();
}
        The Display class
```

### Elevator car
This section contains the definition of the ElevatorCar class. An elevator car contains the instance of Door, Display, and ElevatorPanel. The implementation of this class is represented below:

```java
public class ElevatorCar {
    private int id;
    private Door door;
    private ElevatorState state;
    private Display display;
    private ElevatorPanel panel;

    public void move();
    public void stop();
    public void openDoor();
    public void closeDoor();
}
       The ElevatorCar class
```

```c#
class ElevatorCar {
    private int id;
    private Door door;
    private ElevatorState state;
    private Display display;
    private ElevatorPanel panel;

    public void Move();
    public void Stop();
}
   The ElevatorCar class
```

```python
class ElevatorCar:
    def __init__(self, id, door, state, display, panel):
        self.__id = id
        self.__door = door
        self.__state = state
        self.__display = display
        self.__panel = panel

    def move():
        None

    def stop():
        None
	
	The ElevatorCar class
```

```c++
class ElevatorCar {
    private: 
        int id;
        Door door;
        ElevatorState state;
        Display display;
        ElevatorPanel panel;
        

    public: 
        void move();
        void stop();
};
          The ElevatorCar class
```

```javascript
class ElevatorCar {
    #id;
    #door;
    #state;
    #display;
    #panel;

    constructor(id, door, state, display, panel) {
        this.#id = id;
        this.#door = door;
        this.#state = state;
        this.#display = display;
        this.#panel = panel;
    }

    move();
    stop();
}
        The ElevatorCar class
```

### Door and floor
This section contains the code for the Door and Floor classes. In the Door class, the enumeration DoorState is used and the Floor class contains the instances of Display and HallPanel. The implementation of this class is given below:

```java
public class Door {
    private DoorState state;
    public boolean isOpen();
}

public class Floor {
    private List<Display> display;
    private List<HallPanel> panel;
    
    public boolean isBottomMost();
    public boolean isTopMost();
}
        The Door and Floor classes
```

```c#
class Door {
    private DoorState state;
    public bool IsOpen();
}

class Floor {
    private List<Display> display;
    private List<HallPanel> panel;

    public bool IsBottomMost();
    public bool IsTopMost();
}
       The Door and Floor classes
```

```python
class Door:
    def __init__(self, state):
        self.__state = state
    
    def isOpen():
        pass

class Floor:
    def __init__(self, display, panel):
        self.__display = display
        self.__panel = panel

    def is_bottom_most(self):
        None
    
    def is_top_most(self):
        None
	
   The Door and Floor classes        
```

```c++
class Door {
    private: 
        DoorState state;
    public:
        bool isOpen();
};

class Floor {
    private: 
        vector<Display> display;
        vector<HallPanel> panel;
    public:
        bool isBottomMost();
        bool isTopMost();
};
         The Door and Floor classes
```

```javascript
class Door {
    #status;
    constructor(status) {
        this.#status = status;
    }
    isOpen();
}

class Floor {
    #display;
    #panel;
    constructor() {
        this.#display = new Array();
        this.#panel = new Array();
    }
    isBottomMost();
    isTopMost();
}
        The Door and Floor classes
```

### Elevator system and building
The final class of an elevator system is the ElevatorSystem class which will be a Singleton class, which means that the entire system will have only one instance of this class. Moreover, there is a Building class that contains the instances of Floor and ElevatorCar. The implementation of these Singleton classes are provided below:

```java
public class ElevatorSystem {
    private Building building;
    public void monitoring();
    public void dispatcher();

    // The ElevarSystem is a singleton class that ensures it will have only one active instance at a time
    private static ElevatorSystem system = null;
    
    // Created a static method to access the singleton instance of ElevatorSytem class
    public static ElevatorSystem getInstance() {
        if (system == null) {
            system = new ElevatorSystem();
        }
        return system;
    }
}

public class Building {
    private List<Floor> floor;
    private List<ElevatorCar> elevator; 

    private static Building building = null;
    
    public static Building getInstance() {
        if (building == null) {
            building = new Building();
        }
        return building;
    }
}
         The ElevatorSystem and Building classes
```

```c#
class ElevatorSystem {
    private Building building;
    public void Monitoring();
    public void Dispatcher();

    // The ElevarSystem is a singleton class that ensures it will have only one active instance at a time
    private static ElevatorSystem system = null;
    
    // Created a static method to access the singleton instance of ElevatorSytem class
    public static ElevatorSystem GetInstance() {
        if (system == null) {
            system = new ElevatorSystem();
        }
        return system;
    }
}

class Building {
    private List<Floor> floor;
    private List<ElevatorCar> elevator; 

    private static Building building = null;
    
    public static Building GetInstance() {
        if (building == null) {
            building = new Building();
        }
        return building;
    }
}
             The ElevatorSystem and Building classes
```

```python
class __ElevatorSystem(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__ElevatorSystem, cls).__new__(cls)
    return cls.__instances

class ElevatorSystem(metaclass=__ElevatorSystem):
    def __init__(self, building):
      self.__building = building

    def monitoring():
        None

    def dispatcher():
        None



class __Building(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__Building, cls).__new__(cls)
    return cls.__instances

class Building(metaclass=__Building):
  def __init__(self):
    self.__floor = []
    self.__elevator = []
    
    The ElevatorSystem and Building classes
```

```c++
class ElevatorSystem {
    private:
        Building building;
        static ElevatorSystem system = NULL;
    public: 
        void monitoring();
        void dispatcher();

        static ElevatorSystem getInstance() {
            if (system == NULL) {
            system = new ElevatorSystem();
            }
            return system;
        }
};

class Building {
    private: 
        vector<Floor> floor;
        vector<ElevatorCar> elevator; 
        static Building building = NULL;
    public: 
        static Building getInstance() {
            if (building == NULL) {
            building = new Building();
            }
            return building;
        }
};
            The ElevatorSystem and Building classes
```

```javascript
class ElevatorSystem {
    #building;
    constructor(building){
        this.#building = building;
    }
    monitoring();
    dispatcher();

    // The ElevarSystem is a singleton class that ensures it will have only one active instance at a time
    #system = null;
    
    // Created a static method to access the singleton instance of ElevatorSytem class
    getInstance() {
        if (system == null) {
            system = new ElevatorSystem();
        }
        return system;
    }
}

class Building {
    #floor;
    #elevator; 

    #building = null;
    constructor(){
        this.#floor = new Array();
        this.#elevator = new Array();

    }
    getInstance() {
        if (building == null) {
            building = new Building();
        }
        return building;
    }
}
           The ElevatorSystem and Building classes
```

## Wrapping up
We've explored the complete design of an elevator control system in this chapter. We've looked at how a basic elevator system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
