# Class Diagram for the Amazon Online Shopping System
In this lesson, we’ll identify and design the classes, abstract classes, and interfaces based on the requirements that we have previously gathered from the interviewer in our Amazon shopping system.

## Components of Amazon
As mentioned earlier, we should design the Amazon online shopping system using a bottom-up approach.


### Customer
The Customer abstract class refers to a user trying to buy a product from Amazon. Hence, it can access the items present in the shopping cart through the getShoppingCart() function.

A customer can be one of the following:

1. Authenticated users

2. Guest users

The details of these are given below:

- The AuthenticatedUser class refers to an individual that contains a registered account on Amazon.

- The Guest class refers to an individual without an account who can only search for and view the products on the Amazon website and add them to the shopping cart. However, they need to register an account on Amazon to place an order.

The class diagram of all these is provided below:

[The class diagram of the Customer class and its child classes](./customer.png)

```
R1: A customer can either be an authenticated user or a guest. The authenticated user has a registered account on the Amazon online shopping system, whereas a guest does not have a registered account.
```

### Admin
The Admin class refers to an individual with a registered account on Amazon that can add, modify, or delete product categories and block users.

[The class diagram of the Admin class](./admin.png)

```
R10: An admin should exist that can add or modify product categories and block users.
```
### Account
The Account class accesses and showcases the personal details of the authenticated user and the admin, who are the two types of registered accounts available in the system. Users with an account will have the option to add and access multiple shipping addresses as well as add and delete different products and product reviews.

[The class diagram of the Account class](./account.png)

```
R1: A customer can either be an authenticated user or a guest. The authenticated user is one with a registered account on the Amazon online shopping system, whereas a guest doesn’t have a registered account.
```

### Product
The Product class contains the details of a particular product available on the Amazon shopping store. Each product will fall under a specific category present on Amazon and can have none, one, or more reviews.

[The class diagram of the Product class](./product.png)

```
R3: A product can have multiple reviews and ratings from multiple customers.
```
### Product category
The ProductCategory class contains the names and descriptions of the various categories of products present on Amazon. It will also contain a reference to the list of products under a particular category.

[The class diagram of the ProductCategory class](./productcategory.png)

```
R2: An authenticated user should be able to buy, sell, and search the products via the product name or category. A guest is only able to search for products.
```

### Product review
The ProductReview class contains the rating and review attributes that a registered user can use to add a review about a particular product.

[The class diagram of the ProductReview class](./productreview.png)

```
R3: A product can have multiple reviews and ratings from multiple customers.
```
### Catalog
The Catalog class will contain a list of products of different names or categories.

[The class diagram of the Catalog class]

```
R2: An authenticated user should be able to buy, sell, and search the products via the product name or category. A guest is only able to search for products.
```
### Search
The Search class will be an interface that contains the functionalities relating to searching for products.

[The class diagram of the Search interface]
```
R2: An authenticated user should be able to buy, sell, and search the products via the product name or category. A guest is only able to search for products.
```

### Cart item
The CartItem class refers to the items present in the shopping cart. It will have the price and quantity attributes which can be modified using the updateQuantity() function.

[The class diagram of the CartItem class]
```
R4: An authenticated user should be able to add, remove, or modify product items in their shopping cart. The authenticated user can further check out and buy the items.
```

### Shopping cart
The ShoppingCart class contains the list of cart items, upon which, actions such as adding items to the cart, removing items from the cart, and accessing all cart items can be performed.

[The class diagram of the ShoppingCart class]
```
R4: An authenticated user should be able to add, remove, or modify product items in their shopping cart. The authenticated user can further check out and buy the items.
```

### Order
The Order class refers to a particular order of a customer and will keep track of the order status along with the option of sending the order to shipment. It will also be used to make the payment and log the order details.

[The class diagram of the Order class]

```
R7: An order can be canceled, only in the case that it hasn’t been shipped.
```

### Order log
The OrderLog class keeps a log of the order through its creation date and order status.

[The class diagram of the OrderLog class]
```
R7: An order can be canceled, only in the case that it hasn’t been shipped.
```

### Shipment
The Shipment class keeps track of the date on which the order was shipped, its estimated arrival time, and the shipment method. It will also be used to log the shipment details.

[The class diagram of the Shipment class]

```
R9: Shipment can be tracked to see the current status and the estimated time of arrival for the order.
```
### Shipment log
The ShipmentLog class keeps a log of the shipment through its creation date and shipment status.

[The class diagram of the ShipmentLog class]

```
R9: Shipment can be tracked to see the current status and the estimated time of arrival for the order.
```

### Payment
The Payment class will have three child classes: CreditCard, ElectronicBankTransfer, and Cash since these are the three payment methods available to a customer on Amazon.

[The class diagram of Payment and its child classes]
```
R6: Payment can be made through credit cards, electronic bank transfers, or through cash on delivery.
```

### Notification
The Notification class is responsible for sending order and shipment notifications to customers through either email or SMS, as shown below in the class diagram:
```
Note: Since the Notification class can be extended by adding various other options, we will implement it as an abstract class.
```
[The class diagram of Notification and its child classes]

```
R8: Notifications are sent whenever there is a change in the order or shipping status.
```

### Enumerations
The following is the list of enumerations required in Amazon:

AccountStatus: The account status tells about the user account status, whether it is active, inactive, or blocked.

PaymentStatus: The payment status tells about the user account status, whether it is confirmed, declined, pending, or refunded.

OrderStatus: The order status describes the status of a particular order of a customer, whether it is unshipped, pending, shipped, confirmed, or canceled.hipped, confirmed, or canceled.

ShipmentStatus: The shipment status tells us about the status of an order’s shipment, whether it is in a pending state, shipped state, delivered state, or on hold.

[Enums in Amazon]

### Custom data type
We need to create a custom data type, Address, that will store the location of a customer.

[The class diagram of the Address custom data type]

## Relationship between the classes
Now, we’ll discuss the relationships between the classes we have defined in our Amazon shopping system above.

### Association
- The class diagram has the following association relationships:

- The Guest class has a one-way association with Search.

- The Notification class has a two-way association with ShipmentLog and OrderLog.

- The Product class has a two-way association with Account and CartItem and a one-way association with ProductCategory and ProductReview.

- The ShoppingCart class has a two-way association with CartItem.

- The Order class has a two-way association with CartItem and Payment and a one-way association with Shipment.

[The association relationship between classes]

### Composition
- The class diagram has the following composition relationships:

- The Shipment class is composed of the ShipmentLog class.

- The Account class is composed of the CreditCard, ElectronicBankTranfer, Admin, and AuthenticatedUser classes.

- The AuthenticatedUser class is composed of the Order class which itself is composed of the OrderLog class.

- The Customer class is composed of the ShoppingCart class.

[The composition relationship between classes]

### Aggregation
The following classes show an aggregation relationship:

- The Product class contains the Catalog class.

[The aggregation relationship between classes]

### Generalization
The following classes show a generalization relationship:

- The Catalog class implements the Search class.

[The generalization relationship between classes]

### Inheritance
The following classes show an inheritance relationship:

- Both Guest and AuthenticatedUser extend the Customer class.

- Both EmailNotification and SMSNotification extend the Notification class.

- Subclasses Cash, ElectronicBankTransfer, and CreditCard extend the Payment class.
```
Note: We have already discussed the inheritance relationship between classes in the component section above.
```

## Class diagram of Amazon

[The class diagram of Amazon]

## Design pattern
In the Amazon online shopping system, we can use the Factory design pattern to maintain different orders and the bill generation process based on the products selected by a customer.

We know that in the Amazon-online shopping system, various items are on sale, or items can be bought using special coupons that give different percentage discounts. To effectively calculate prices for different discount types, we can use the Strategy design pattern. This pattern allows us to design a separate strategy or algorithm to calculate the prices for each discount type.

## Additional requirements
The interviewer can introduce some additional requirements in the Amazon shopping system, or they can ask some follow-up questions. Let’s see some examples of additional requirements:

Wish list: Only users with an account (an authenticated user) can add a product to their wishlist. The WishList class can be used to move products to a cart and also check if it is currently available:


[Adding WishList functionality]

Discount: A discount will be applied to the payment depending on special events such as Christmas, Black Friday, and so on. The class diagram provided below shows the relationship of Discount with the Payment class:

[Relationship between the Discount class with the Payment class]

We’ve completed the class diagram of the Amazon shopping system according to the requirements. Now let’s design the sequence diagram of the Amazon shopping system in the next lesson.
