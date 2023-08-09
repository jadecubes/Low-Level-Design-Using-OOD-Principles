# Use Case Diagram for the Amazon Online Shopping System
Let’s build the use case diagram of the Amazon problem and understand the relationship between its different components.

First, we’ll define the different elements of Amazon, followed by the complete use case diagram of the system.

## System
Our system is the "Amazon shopping system."

## Actors
Now, we’ll define the main actors of Amazon.

### Primary actors
- Authenticated user: This actor can search for products using the catalog, place or cancel orders, and add new products to sell.

- Guest: The guest actor can search for products using the catalog, add items to a shopping cart and update it. However, it needs to become a registered/authenticated member to place an order.

### Secondary actors
- Admin: This can add, remove, or update an account as well as add, modify, or delete existing product categories.

- System: This is responsible for sending out notifications for orders and shipping updates.

## Use Cases
In this section, we will define the use cases for Amazon. We have listed down the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Admin
- Login/Logout: To log in or log out of your account on Amazon

- Block/Unblock/Update/Delete account: To block, unblock, or delete an account as well as modify account details

- Add/Modify/Delete product category: To add, modify, or delete product categories

- Modify product: To modify the details of any existing product

### Authenticated user
- Register account: To register for an account on Amazon

- Login/Logout: To log in or log out of your account on Amazon

- Update/Delete account: To delete an account or modify their own account details

- Add/Modify/Delete product: To add a new product or modify the details of any existing product that a customer themselves added for selling. A user can also delete a product that they added for selling

- Search product: To search for any particular product based on the given criteria (name or category)

- Add item to shopping cart: To add an item to a shopping cart

- Update shopping cart: To update the item quantities present in the shopping cart

- Checkout shopping cart: To check out from the shopping cart into the payment section

- Add shipping address: To add a shipping address

- Add credit card: To pay the order amount via credit card

### Guest
- Register account: To register for an account on Amazon

- Search product: To search for any particular product based on the given criteria (name or category)

- Add item to shopping cart: To add an item to a shopping cart

- Update shopping cart: To update the item quantities present in the shopping cart

### System
- Send order notification: To send a notification of an order after payment

- Send shipment update notification: To send a notification of any updates in shipment
## Relationships
We describe the relationships between and among actors and their use cases in this section.

### Generalization
- The “Authenticated User” actor has a generalization relationship with the “Guest” actor, as an authenticated user can perform all those tasks that a guest can perform.

- We can search for a product by category and by product name. This shows that the “search product” use case has a generalization relationship with the “By product category catalog” and “By product name catalog” use cases.

### Associations
The table below shows the association relationship between actors and their use cases.

```
Admin                                   Authenticated User                                   Guest                                   System

Login/Logout                            Register account                                   Register account                        Send order notification

Update/delete account                   Login/Logout                                       Search product                          Send shipment update notification

Block/Unblock account                   Update/delete account                              Add item to shopping cart

Add/modify product category             Add/modify product                                 Update shopping cart

Modify product                          Search product

                                        Add item to shopping cart

                                        Update shopping cart

                                        Checkout shopping cart

                                        Add shipping address

                                        Add credit card
```
### Include
- The “Add product” and “Modify product” use cases have an include relationship with the “Update catalog” use case since the catalog needs to be updated as well when any new product is added or the details of an existing product are modified.

- The “Make payment” use case has an include relationship with the “Send order notification” use case, since once the payment has been made and verified, only then will the system generate a notification.

- The “Cancel order” use case has an include relationship with the “Refund payment” use case, since this is part of the process.

## Use case diagram
