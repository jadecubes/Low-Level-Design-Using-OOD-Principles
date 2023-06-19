# Class Diagram for the Library Management System
Here, we’ll create the class diagram for our system on the basis of the requirements that we gathered previously. In the class diagram, we will first design/create the classes, abstract classes, and interfaces for the system, and then we’ll identify the relationship between classes in accordance with all requirements of the library management system.

## Components of a library management system
In this section, we will define the classes for LMS. Since we are following the bottom-up approach for designing a class diagram, we’ll first create the classes of small components. After that, we will integrate those components and create the class diagram for the whole library management system.

### Book and book item
Book is an abstract class in which the complete information of the book is stored like ISBN, title, subject, etc. Since the book can be written by many authors, there is a complex member named authors in the class representing the list of book authors. The Book class consists of the enum BookFormat for encountering the different book types. It will be helpful in displaying the catalog and assists in searching as well.

The BookItem class extends the Book class, which represents a single and unique copy of the book. Each book item has its price, rack information, etc. related to it. A particular book is placed in a particular position in the library. So, the Rack type object will take care of where the book is placed. This class is using an enum BookStatus to keep track of the current status of the book. All the book borrowing and purchasing information is associated with the BookItem class. The UML representation of Book and BookItem is shown in the class diagram below:

[The class diagram of the Book and BookItem classes]

```
R3: Every book should have an associated ISBN, title, author name, subject, and publication date.

R4: There can be multiple copies of the book. Each copy will be recognized as a book item.

ISBN: International Standard Book Number
```

### Rack
We have seen a complex object Rack that was defined in the BookItem class. Now, we are going to create a Rack class. This class is used to identify the physical location of any book item in the library. Every rack has a specific rack number assigned to it and a location identifier to represent the exact location of the book item in the library. The visual representation of the class is as follows:

[The class diagram of the Rack class]

```
R2: Every book is supposed to have a unique identification number and other details including a rack number to help locate the book physically.
```

### Person and author
The Person class is used to store information related to a person like a name, email, phone number, etc. In the person class, there is an object of the Address class to specify the person’s address.

There is also a class named Author that stores the author’s data like the author’s name and description. The author’s information is also used in the Book class.

The representation of both classes is as follows:

[The class diagram of the Person and Author classes]

### User, librarian, and library member
User is an abstract class that represents the system users of LMS. There can be two types of users: librarians and library members.

The Librarian class is a derived class of the User class. This class is responsible for adding a new book item and blocking or unblocking any library member.

Similar to the Librarian class, the Member class also extends the User class. The variable totalBooksCheckedout is used to store the number of books a certain member has already checked out. A member can reserve a book, return a book, or renew an already reserved book.

Since the Librarian and Member classes extend the User class, their class diagram representation would be as follows:

[The class diagram of the User, Librarian, and Member classes]

```
R5: There can be two types of users: the librarian and the members.

R11: The system should allow the user to renew the reserved book.
```

### Library card
To manage each user’s library card information, we have a LibraryCard class. Each library card has an identification number, issue date, and information on whether or not it is active. The class representation of the LibraryCard class is as follows:
[The class diagram of the LibraryCard class]

```
R6: Every user must have a library card with a unique card number.
```

### Book reservation
Book reservation is one of the most important requirements of the library management system. To fulfill this functionality, we have a class named BookReservation. This class is responsible for managing the book reservation status of the book items.

The UML representation of the class is shown below:

[The class diagram of the BookReservation class]

```
R10: The system should be able to keep a record of who issued or reserved a particular book and on which date.
```

### Book lending
Similar to book reservations, book lending is also a part of the system since the BookLending class manages the process of checking out the book items. The information like the book lending date, due date, return date, etc. is being handled or processed in this class.

Here is what the class definition looks like:

[The class diagram of the BookLending class]

### Notification
Notification is an abstract class. If the book is not returned within the due date, then the class notification is responsible for informing library members by sending a notification. Every notification has an ID, creation date, and content in it. The notification can be either a postal notification or an email notification.

The PostalNotification class requires the address of the library member to send a notification while EmailNotification needs the email address of the library member to send a notification.

The relationship diagram of these classes is shown below:

[The class diagram of the Notification, PostalNotification, and EmailNotification classes]

```
R12: The system should send a notification if the book is not returned within the due date.
```

### Search and catalog
Search is one of the most important functionalities of the system. Search is the interface that allows the user to search for any book and return the list of books upon searching by any of the following methods:

- Search a book by its title.

- Search a book by its author name.

- Search a book by its subject.

- Search a book by its publication date.

Catalog is a class where the search functionality is implemented. In each catalog, the books are sorted according to one of the given search techniques, i.e., on the basis of the book’s title, author, subject, or publication date.

The following UML diagram shows this relationship:

[The class diagram of the Search and Catalog classes]

```
R14: The system should allow the user to search a book by its title, author name, subject, or publication date.
```

### Library
The Library class is the base class of the system which is used to represent the library. It is a central part of the organization. This class consists of two members: name and Address. The string type name is used to store the name of the library, while the complex object Address is to store the complete address location of the library. The UML representation of the Library class is as follows:

[The class diagram of the Library class]

### Enumerations
Enumeration is generally a data type in which only a specific set of constants can be stored. The following is a list of enumerations required in LMS:

BookFormat: This describes that a book can only be of one of the specified formats. It can be a hardcover, paperback, audiobook, e-book, newspaper, magazine, or journal.

BookStatus: The book status describes the status of the particular book item for the user, whether it is available, reserved, loaned, or lost.

ReservationStatus: This tells about the reservation state of any book item, whether it is in a waiting state, pending state, canceled state, or none of them.

AccountStatus: The account status tells about the user account status, whether it is active, closed, canceled, blacklisted, or none.

[Enums in the library management system]

### Custom data type
The Address is a custom data type, that will store the address of a library and the library users.

[Class diagram of the Address custom data type]

## Relationship between the classes

Now, we are going to discuss the relationships between the classes we have defined above in our library management system.

### Association
The class diagram has the following association relationships:

#### One-way association
- The User has a one-way association with BookItem and BookReservation.

- Both BookReservation and BookLending have a one-way association with the BookItem.
[The one-way association relationship between the classes]

#### Two-way association
- Author has a two-way association with Book.

- Both Rack and Librarian have a two-way association with BookItem.

- The Notification has a two-way association with BookLending and BookReservation.

- The BookLending has a two-way association with BookReservation and User.

[The two-way association relationship between the classes]

### Composition
- Library is composed of BookItem.

- User is composed of LibraryCard.

[The composition relationship between the classes]

### Aggregation
- The Catalog class contains the Book class.

[The aggregation relationship between the classes]
### Inheritance
The following classes show an inheritance relationship:

- Both Librarian and Member classes extend the User class.

- Both EmailNotification and PostalNotification classes extend the Notification class.

- The BookItem class extends the Book class.

- The Catalog class implements the Search interface.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```

## Class diagram of the library management system
[The class diagram of the library management system]

## Design pattern
We can apply the Factory design pattern to create objects and mandate that they go via a single factory. For example, we can create a BookFactory class to create a book object in an arranged manner.

Similarly, we can use the Delegation design pattern to delegate a task from one class to another class. For example, librarian functionalities like adding book items, deleting book items, or modifying book items are actually implemented in the BookItem class. The Librarian class uses the BookItem class and has access to its data and methods.

Moreover, we can use the Observer design pattern to notify library members. For example, if a member searches for a book that is unavailable at that time, then the observer interface system will notify the member when that book is available for reservation.


## Additional requirements
The interviewer can introduce some additional requirements in LMS, or they can ask some follow-up questions. Let’s see an example of additional requirements:

Barcode Reader: Each member should have a unique barcode on their library card and each book should also have a distinct barcode associated with it, and the system should be able to scan the barcode of every book and member. To fulfill this requirement, we have the class diagram shown below:

[Relationship between the BarcodeReader and the LibraryCard class]

FineTransaction: Since there is a fine for not returning the book within the time, there should exist some mechanism to pay the fine. There are three ways to pay the fine: check transaction, cash transaction and credit card transaction.

The fine payment functionality follows the Decorator pattern as the fine keeps on adding upon the increased number of days. The class diagram provided below shows the relationship of FineTransaction with the Fine class:

[Relationship of the FineTransaction class with other classes]

```
Question
Let’s say that the interviewer asks you what would happen if two or more members try to reserve the same book item. Which member will get the book?

Answer
If two or more members try to reserve the book item at the same time, then the process will be executed on a First Come First Serve (FCFS) basis. Like the member who comes first gets the book reserved. If two members come at the same time, then the system will check which member has less number of checked out books through totalBooksCheckedOut and reserve the book item for that particular member.

If both members have already reached the maximum limit of checkouts, then no one will be able to reserve a book.

Note: The member would be able to reserve a book that is currently not available so that they get this book first whenever it will be available.
```
We have successfully designed the class diagram for the library management system. Let’s move to the next lesson to see how we can construct the sequence diagram for the system.
