# Code for the Amazon Locker Service
We've gone over the different aspects of the Amazon Locker service and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the Amazon Locker service using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the Amazon Locker service:

- Java

- C#

- Python

- C++

- JavaScript

## Amazon Locker service classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Enumerations
First, we will define all the enumerations used in the Amazon Locker service. According to the class diagram, there are two enumerations in the system, i.e., LockerSize and LockerState The code to implement these enumerations is as follows:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze()  method as an alternative that freezes an object and prevents further modifications.
```
```
enumerations: A special data type which contains a set of predefined constants.
```

```java
// definition of enumerations used in the Amazon Locker service
public enum LockerSize {
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
}
public enum LockerState {
    CLOSED,
    BOOKED,
    AVAILABLE
}
```

```c#
// definition of enumerations used in the Amazon Locker service
enum LockerSize {
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
}
enum LockerState {
    CLOSED,
    BOOKED,
    AVAILABLE
}
            Constant definitions

```

```python
# definition of enumerations used in the Amazon Locker service
class LockerSize(enum.Enum):
    EXTRA_SMALL = 1
    SMALL = 2
    MEDIUM = 3
    LARGE = 4
    EXTRA_LARGE = 5
    DOUBLE_EXTRA_LARGE = 6
}
class LockerState(enum.Enum):
    CLOSED = 1
    BOOKED = 2
    AVAILABLE = 3
}
        Constant definitions

```

```c++
// definition of enumerations used in the Amazon Locker service
enum LockerSize {
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
}
enum LockerState {
    CLOSED,
    BOOKED,
    AVAILABLE
}

              Constant definitions
```

```javascript
// definition of enumerations used in the Amazon Locker service
const LockerSize = Object.freeze({
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
});
const LockerState = Object.freeze({
    CLOSED,
    BOOKED,
    AVAILABLE
});

Constant definitions

```

### Item and Order
The Item class represents the single item while the Order represents the order placed by the customer and can contain the list of items. The definition of these two classes is given below:


### Package and LockerPackage
### Locker and LockerLocation
### LockerService and Notification
## Wrapping up
