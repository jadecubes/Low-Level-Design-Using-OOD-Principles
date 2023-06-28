# Class Diagram for the Vending Machine
In this lesson, we’ll identify and design the classes and interfaces based on the requirements that we have previously gathered from the interviewer for our vending machine system.

## Components of a vending machine
As mentioned earlier, we should design the vending machine using a bottom-up approach.

### State
State is an interface that represents the current state of the vending machine. There can be three possible states of a vending machine, i.e., no money inserted state, money inserted state, and the dispense state. The NoMoneyInsertedState class represents the state when there is no money inserted in the machine. When the user inserts the money into the machine, the state changes to MoneyInsertedState. Furthermore, when the machine dispenses the required product to the user, it transitions to the DispenseState.

This problem follows the State design pattern since the vending machine changes its behavior based on its state. Here, the State class defines an interface for declaring what the subclasses (NoMoneyInsertedState, MoneyInsertedState, DispenseState) should do. The subclasses provide the implementation for methods defined in the State, and the implementation of each method changes with the change of the state. Every state implements some functions, as shown below:

[The class diagram of the State interface and its subclasses](./classdiagram.png)

```
R2: The vending machine can be in one of these three states:

- There is no money inserted into the machine.

- Money is inserted into the machine.

- The machine gives out the product.
```
```
Note: According to the implementation of the State design pattern, all functions will be available in each state. However, it is not necessary that every function has a meaningful definition for that particular state.
```

### Product
The Product class contains the details of a particular product available in the vending machine. Each product has name, id, price, and its type associated with it as presented below:

[The class diagram of the Product class](./product.png)

### Rack
The Rack class is used to identify the location of the product in the vending machine. Every rack has a specific rackNumber as an identifier. The class representation is provided below:

[The class diagram of the Rack class](./rack.png)

```
R1: There are different products placed at different positions in the vending machine.
```

### Inventory
The Inventory class will contain a list of products available at different positions inside the vending machine. It will also reference the name of the product present in the particular rack. This class is also responsible for adding a product to the vending machine. The class representation is provided below:

[The class diagram of the Inventory class](./inventory.png)

```
R4: The admin can add a product to the machine or remove a product from the machine.
```

### Vending machine
VendingMachine is a class that represents the whole vending machine. The State type variable is used to define the current state of the vending machine. The vending machine has a list of racks and amount stored in it. This class follows the Singleton design pattern, since there will only be one instance of the class. The class is presented below:

[The class diagram of the VendingMachine class](./vendingmachine.png)

```
R6: The user can insert money into the machine in the form of cash.

R8: The system should check whether the user has inserted the exact amount required for the specific product into the machine.

R9: If the amount is greater than the product price, the system should change back the user and dispense the product.

R10: If the amount is less than the product price, the system should display an error message, and return the money.
```

### Enumeration
The enumeration required to design the vending machine system is provided below:

#### ProductType
We need to create an enumeration to keep track of the type of product, whether it is a chocolate, snack, beverage, or other.

[The ProductType enumeration](./enum.png)
## Relationship between the classes
Now, we’ll discuss the relationships between the classes we have defined above in our vending machine.

### Composition
The class diagram has the following composition relationships.

- The VendingMachine class is composed of the Rack class.

- The Inventory class is composed of the Product class.

[The composition relationship between classes](./composition.png)

### Aggregation
The class diagram has the following aggregation relationships:

- The VendingMachine class contains the State interface.

[The aggregation relationship between classes](./agg.png)
### Association
The class diagram has the following association relationships.

- The VendingMachine class has a two-way association with the Inventory class.

- The Rack class has a two-way association with the Product class.

[The association relationship between classes](./association.png)
### Inheritance
The following classes show an inheritance relationship:

- The NoMoneyInsertedState, MoneyInsertedState, and DispenseState classes implement the State interface.
```
Note: We have already discussed this inheritance relationship between classes in the component section above.
```
## Class diagram for the vending machine

[The class diagram of the vending machine](./classdiagram2.png)
## Design pattern
We have used the State design pattern to design this problem because, in different states, we perform different or specific tasks according to the state. The vending machine changes its behavior based on its state. The different states within the system are listed below:

- No money inserted state

- Money inserted state

- Dispense state

All these states have the same methods but the implementation of each method in each state changes with the change of the state.

## Additional requirements
The interviewer can introduce some additional requirements in the vending machine, or they can ask some follow-up questions. Let's see some examples of additional requirements:

Refund/Cancel: The vending machine should have the option to cancel the operation. In that case, the customers will get a refund. The class diagram provided below shows the refund functionality in all states:

[Modified class diagram of the vending machine](./additional.png)

In the class diagram above, we can see a function, refundFullMoney(), in all states which is used to refund the full money. Here is the definition of the refundFullMoney() function according to each state:

- NoMoneyInsertedState: In this state, the refundFullMoney() function throws an exception or warning, “please insert some cash first” because we we have not inserted any money yet.

- MoneyInsertedState: In this state, we know the customer inserted the cash because, due to this, we shifted the state of the vending machine from NoMoneyInsertedState to MoneyInsertedState. If the customer uses the refund option, then the refundFullMoney() function will call and return the full amount back in the change tray.

- DispenseState: In this state, the refundFullMoney() function is blocked. We can say that if the customer uses the refund option, then the system does not do anything. This is because, in this state, the customer has already selected a product, and the vending machine is in the dispense state.

We have completed the class diagram of a vending machine according to the requirements. Now let's go ahead and design the activity diagram of the vending machine in the next lesson.
