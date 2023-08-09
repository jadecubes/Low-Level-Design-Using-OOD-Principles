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

[The class diagram of the Customer class and its child classes]

```
R1: A customer can either be an authenticated user or a guest. The authenticated user has a registered account on the Amazon online shopping system, whereas a guest does not have a registered account.
```

### Admin
The Admin class refers to an individual with a registered account on Amazon that can add, modify, or delete product categories and block users.

[The class diagram of the Admin class]

```
R10: An admin should exist that can add or modify product categories and block users.
```
### Account
The Account class accesses and showcases the personal details of the authenticated user and the admin, who are the two types of registered accounts available in the system. Users with an account will have the option to add and access multiple shipping addresses as well as add and delete different products and product reviews.

[The class diagram of the Account class]

```
R1: A customer can either be an authenticated user or a guest. The authenticated user is one with a registered account on the Amazon online shopping system, whereas a guest doesn’t have a registered account.
```

### Product
The Product class contains the details of a particular product available on the Amazon shopping store. Each product will fall under a specific category present on Amazon and can have none, one, or more reviews.

[The class diagram of the Product class]

```
R3: A product can have multiple reviews and ratings from multiple customers.
```
### Product category
The ProductCategory class contains the names and descriptions of the various categories of products present on Amazon. It will also contain a reference to the list of products under a particular category.

[The class diagram of the ProductCategory class]

```
R2: An authenticated user should be able to buy, sell, and search the products via the product name or category. A guest is only able to search for products.
```

### Product review
The ProductReview class contains the rating and review attributes that a registered user can use to add a review about a particular product.

[The class diagram of the ProductReview class]

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
### Order log
### Shipment
### Shipment log
### Payment
### Notification
### Enumerations
### Custom data type
## Relationship between the classes
### Association
### Composition
### Aggregation
### Generalization
### Inheritance
## Class diagram of Amazon
## Design pattern
## Additional requirements
