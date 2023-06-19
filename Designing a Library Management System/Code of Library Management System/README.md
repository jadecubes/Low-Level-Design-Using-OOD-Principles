# Code of Library Management System
We’ve gone over the different aspects of the library management system and observed the attributes attached to the problem using various UML diagrams. Let us now explore the more practical side of things, where we will work on implementing the library management system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the library management system:

- Java

- C#

- Python

- C++

- JavaScript

## Library management
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations
First, we will define all the enumerations required in the library management system. According to the class diagram, there are four enumerations used in the system: BookFormat, BookStatus, ReservationStatus, and AccountStatus. The code to implement these enumerations is as follows:`
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```
```java
// definition of enumerations used in library management system
enum BookFormat {
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL
}

enum BookStatus {
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST
}

enum ReservationStatus {
    WAITING,
    PENDING,
    CANCELED,
    NONE
}

enum AccountStatus {
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
}
            Enum definitions
```

```c#
// definition of enumerations used in library management system
enum BookFormat {
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL
}
  
enum BookStatus {
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST
}

enum ReservationStatus {
    WAITING,
    PENDING,
    CANCELED,
    NONE
}

enum AccountStatus {
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
}
            Enum definitions
```

```python

# definition of enumerations used in library management system
class BookFormat(Enum):
  HARDCOVER = 1
  PAPERBACK = 2
  AUDIOBOOK = 3
  EBOOK = 4
  NEWSPAPER = 5
  MAGAZINE = 6
  JOURNAL = 7


class BookStatus(Enum):
  AVAILABLE = 1
  RESERVED = 2
  LOANED = 3
  LOST = 4


class ReservationStatus(Enum):
  WAITING = 1
  PENDING = 2
  CANCELED = 3
  NONE = 4


class AccountStatus(Enum):
  ACTIVE = 1
  CLOSED = 2
  CANCELED = 3
  BLACKLISTED = 4
  NONE = 5
  
              Enum definitions
```

```c++
// definition of enumerations used in library management system
enum BookFormat {
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL
};
  
enum BookStatus {
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST
};

enum ReservationStatus{
    WAITING,
    PENDING,
    CANCELED,
    NONE
};

enum AccountStatus{
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
};
               Enum definitions
```

```javascript
const BookFormat = Object.freeze({
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL

});
  
const BookStatus  = Object.freeze({
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST

});

const ReservationStatus = Object.freeze({
    WAITING,
    PENDING,
    CANCELED,
    NONE

});

const AccountStatus = Object.freeze({
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
});
             Enum definitions
```

### Address and person
This section contains the code for Address and Person classes where the Person class is composed of an Address class. The implementation of these classes can be found below:
```java
public class Address {
    private String streetAddress;
    private String city;
    private String state;
    private int zipCode;
    private String country;
}

public class Person {
    private String name;
    private Address address;
    private String email;
    private String phone;
}
          The Address and Person classes
```

```c#
class Address {
    private String streetAddress;
    private String city;
    private String state;
    private int zipCode;
    private String country;
}

class Person {
    private String name;
    private Address address;
    private String email;
    private String phone;
}
        
        The Address and Person classes
```

```python
class Address:
  def __init__(self, street, city, state, zip_code, country):
    self.__street_address = street
    self.__city = city
    self.__state = state
    self.__zip_code = zip_code
    self.__country = country


class Person(ABC):
  def __init__(self, name, address, email, phone):
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone = phone
              
              The Address and Person classes
```

```c++
class Address {
    private:
        string streetAddress;
        string city;
        string state;
        int zipCode;
        string country;
};

class Person {
    private:
        string name;
        Address address;
        string email;
        string phone;
};
     The Address and Person classes
```

```javascript
class Address {
    #streetAddress;
    #city;
    #state;
    #zipCode;
    #country;
}

class Person {
    #name;
    #address;
    #email;
    #phone;
}

         The Address and Person classes
```


### User
The User is an abstract class that represents the various people or actors that can interact with the system. Since there are two types of users, the librarian and the library member, the user can either be a Librarian or a Member. The implementation of the mentioned classes is shown below:

```java
// User is an abstract class
public abstract class User {
    private String id;
    private String password;
    private AccountStatus status;
    private Person person;
    private LibraryCard card;

    public abstract boolean resetPassword();
}

public class Librarian extends User {
    public boolean addBookItem(BookItem bookItem);
    public boolean blockMember(Member member);
    public boolean unBlockMember(Member member);
    public boolean resetPassword() {
        // definition
    }
}

public class Member extends User {
    private Date dateOfMembership;
    private int totalBooksCheckedOut;

    public boolean reserveBookItem(BookItem bookItem);
    private void incrementTotalBooksCheckedOut();
    public boolean checkoutBookItem(BookItem bookItem); 
    private void checkForFine(String bookItemId);
    public void returnBookItem(BookItem bookItem);
    public boolean renewBookItem(BookItem bookItem);
    public boolean resetPassword() {
        // definition
    }
}

       User and its child classes
```

```c#
// User is an abstract class
public abstract class User {
    private String id;
    private String password;
    private AccountStatus status;
    private Person person;
    private LibraryCard card;

    public abstract boolean ResetPassword();
}

class Librarian : User {
    public bool AddBookItem(BookItem bookItem);
    public bool BlockMember(Member member);
    public bool UnBlockMember(Member member);
    public override bool ResetPassword();
}

class Member : User {
    private DateTime dateOfMembership;
    private int totalBooksCheckedOut;

    public bool ReserveBookItem(BookItem bookItem);
    private void IncrementTotalBooksCheckedout();
    public bool CheckoutBookItem(BookItem bookItem); 
    private void CheckForFine(String bookItemBarcode);
    public void ReturnBookItem(BookItem bookItem);
    public bool RenewBookItem(BookItem bookItem);
    public override boolean ResetPassword();
}

         User and its child classes
```

```python
# User is an abstract class
from abc import ABC, abstractmethod

class User(ABC):
  def __init__(self, id, password, person, status=AccountStatus.ACTIVE, card):
    self.__id = id
    self.__password = password
    self.__status = status
    self.__person = person
    self.__card = card

  @abstractmethod
  def reset_password(self):
    pass


class Librarian(User):
  def __init__(self, id, password, person, status=AccountStatus.ACTIVE):
    super().__init__(id, password, person, status)

  def add_book_item(self, book_item):
    None

  def block_member(self, member):
    None

  def unblock_member(self, member):
    None

  def reset_password(self):
    pass


class Member(User):
  def __init__(self, id, password, person, status=AccountStatus.ACTIVE):
    super().__init__(id, password, person, status)
    self.__date_of_membership = datetime.date.today()
    self.__total_books_checked_out = 0

  def reserve_book_item(self, book_item):
    None

  def increment_total_books_checked_out(self):
    None

  def checkout_book_item(self, book_item):
    None

  def check_for_fine(self, book_item_barcode):
    None

  def return_book_item(self, book_item):
    None

  def renew_book_item(self, book_item):
    None
    
  def reset_password(self):
    pass
    
          User and its child classes
 ```
 
 ```c++
 // User is an abstract class
class User {
    private: 
        string id;
        string password;
        AccountStatus status;
        Person person;
        LibraryCard card;

    public: 
        virtual bool resetPassword() = 0;
};

class Librarian : public User {
    public: 
        bool addBookItem(BookItem bookItem);
        bool blockMember(Member member);
        bool unBlockMember(Member member);
        bool resetPassword() {
            // definition
        }
};

class Member : User {
    private: 
        time_t dateOfMembership;
        int totalBooksCheckedout;

    public: 
        bool reserveBookItem(BookItem bookItem);
        void incrementTotalBooksCheckedout();
        bool checkoutBookItem(BookItem bookItem); 
        void checkForFine(String bookItemBarcode);
        void returnBookItem(BookItem bookItem);
        bool renewBookItem(BookItem bookItem);
        bool resetPassword() {
            // definition
        }
};

      User and its child classes
```

```javascript
class User {
    #id;
    #password;
    #status;
    #person;
    #card

    constructor(id, password, status, person, card) {
        if (this.constructor == User) {
            throw new Error("Abstract classes can't be instantiated.");
        }
    }

    resetPassword();
}

class Librarian extends User {
    constructor(id, password, status, person, card) {
        this.#id = id;
        this.#password = password;
        this.#status = status;
        this.#person = person;
        this.#card = card;
    }

    addBookItem(bookItem);
    blockMember(member);
    unBlockMember(member);
    resetPassword() {};
}

class Member extends User {
    #dateOfMembership;
    #totalBooksCheckedOut;

    constructor(id, password, status, person, card, membership, books) {
        this.#id = id;
        this.#password = password;
        this.#status = status;
        this.#person = person;
        this.#card = card;
        this.#dateOfMembership = membership;
        this.#totalBooksCheckedOut = books;
    }

    reserveBookItem(bookItem);
    incrementTotalBooksCheckedout();
    checkoutBookItem(bookItem); 
    checkForFine(bookItemBarcode);
    returnBookItem(bookItem);
    renewBookItem(bookItem);
    resetPassword() {};
}

               User and its child classes
```
### Book reservation, book lending and fine
This component shows the implementation of BookReservation, BookLending, and Fine classes. These classes will be responsible for managing reservations against books, managing reservations, and calculating fine on books. The code is shown below:

```java
public class BookReservation {
    private String itemId;
    private Date creationDate;
    private ReservationStatus status;
    private String memberId;

    public static BookReservation fetchReservationDetails(String bookItemId);
}

public class BookLending {
    private String itemId;
    private Date creationDate;
    private Date dueDate;
    private Date returnDate;
    private String memberId;

    public static boolean lendBook(String bookItemId, String memberId);
    public static BookLending fetchLendingDetails(String bookItemId);
}

public class Fine {
    private Date creationDate;
    private String bookItemId;
    private String memberId;

    public static void collectFine(String memberId, long days);
}

         The BookReservation, BookLending and Fine classes
```

```c#
class BookReservation {
    private DateTime creationDate;
    private ReservationStatus status;
    private String memberId;
    private String ItemId;

    public static BookReservation FetchReservationDetails(String bookItemId);
}

class BookLending {
    private String ItemId;
    private DateTime creationDate;
    private DateTime dueDate;
    private DateTime returnDate;
    private String memberId;

    public static bool LendBook(String bookItemId, String memberId);
    public static BookLending FetchLendingDetails(String bookItemId);
}

class Fine {
    private DateTime creationDate;
    private double bookItemBarcode;
    private String memberId;

    public static void CollectFine(String memberId, long days);
}
      The BookReservation, BookLending and Fine classes
```

```python
class BookReservation:
  def __init__(self, creation_date, status, item_id, member_id):
    self.__creation_date = creation_date
    self.__status = status
    self.__item_id = item_id
    self.__member_id = member_id

  def fetch_reservation_details(self, book_item_id):
    None


class BookLending:
  def __init__(self, creation_date, due_date, book_item_id, member_id):
    self.__creation_date = creation_date
    self.__due_date = due_date
    self.__return_date = None
    self.__book_item_id = book_item_id
    self.__member_id = member_id

  def lend_book(self, item_id, member_id):
    None

  def fetch_lending_details(self, item_id):
    None


class Fine:
  def __init__(self, creation_date, book_item_id, member_id):
    self.__creation_date = creation_date
    self.__book_item_id = book_item_id
    self.member_id = member_id

  def collect_fine(self, member_id, days):
    None
           The BookReservation, BookLending and Fine classes
```

```c++
class BookReservation {
    private: 
        time_t creationDate;
        ReservationStatus status;
        string memberId;
        string itemId;

    public: 
        static BookReservation fetchReservationDetails(string bookItemId);
};

class BookLending {
    private: 
        string itemId
        time_t creationDate;
        time_t dueDate;
        time_t returnDate;
        string memberId;

    public: 
        static bool lendBook(string bookItemId, string memberId);
        static BookLending fetchLendingDetails(string bookItemId);
};

class Fine {
    private: 
        time_t creationDate;
        double bookItemBarcode;
        string memberId;

    public: 
        static void collectFine(string memberId, long days);
};
       The BookReservation, BookLending and Fine classes
```

```javascript
class BookReservation {
    #itemId;
    #creationDate;
    #status;
    #memberId;
    
    constructor(itemId, creationDate, status, memberId) {
        this.#itemId = itemId;
        this.#creationDate = creationDate;
        this.#status = status;
        this.#memberId = memberId;
    }
    fetchReservationDetails(bookItemId);
}

class BookLending {
    #itemId;
    #creationDate;
    #dueDate;
    #returnDate;
    #memberId;

    constructor(itemId, creationDate, dueDate, returnDate, memberId) {
        this.#itemId = itemId;
        this.#creationDate = creationDate;
        this.#dueDate = dueDate;
        this.#returnDate = returnDate;
        this.#memberId = memberId;
    }

    lendBook(bookItemId, memberId);
    fetchLendingDetails(bookItemId);
}

class Fine {
    #creationDate;
    #bookItemId;
    #memberId;

    constructor(itemId, creationDate, bookItemId, memberId) {
        this.#creationDate = creationDate;
        this.#bookItemId = bookItemId;
        this.#memberId = memberId;
    }

    collectFine(memberId, days);
}

         The BookReservation, BookLending and Fine classes
```

### Book and rack
The Book is an abstract class and BookItem represents each copy of the book. For example, if there are two copies of the same book then there would only be one Book object and two BookItem objects. The code to implement these classes is as follows:

```java
// User is an abstract class
public abstract class Book {
    private String isbn;
    private String title;
    private String subject;
    private String publisher;
    private String language;
    private int numberOfPages;
    private BookFormat bookFormat;
    private List<Author> authors;
}

public class BookItem extends Book {
    private String id;
    private boolean isReferenceOnly;
    private Date borrowed;
    private Date dueDate;
    private double price;
    private BookStatus status;
    private Date dateOfPurchase;
    private Date publicationDate;
    private Rack placedAt;

    public boolean checkout(String memberId);
}

public class Rack {
    private int number;
    private String locationIdentifier;
}

The Book, BookItem and Rack classes

```

```c#
// User is an abstract class
public abstract class Book {
    private String isbn;
    private String title;
    private String subject;
    private String publisher;
    private String language;
    private int numberOfPages;
    private BookFormat bookFormat;
    private List<Author> authors;
}

class BookItem : Book {
    private String Id;
    private bool isReferenceOnly;
    private DateTime borrowed;
    private DateTime dueDate;
    private double price;
    private BookStatus status;
    private DateTime dateOfPurchase;
    private DateTime publicationDate;
    private Rack placedAt;

    public bool checkout(String memberId);
}

class Rack {
    private int number;
    private String locationIdentifier;
}

The Book, BookItem and Rack classes

```

```python
# User is an abstract class
from abc import ABC, abstractmethod

class Book(ABC):
  def __init__(self, isbn, title, subject, publisher, language, number_of_pages, book_format):
    self.__isbn = isbn
    self.__title = title
    self.__subject = subject
    self.__publisher = publisher
    self.__language = language
    self.__number_of_pages = number_of_pages
    self.__book_format = book_format
    self.__authors = []


class BookItem(Book):
  def __init__(self, id, is_reference_only, borrowed, due_date, price, status, date_of_purchase, publication_date, placed_at):
    self.__id = id
    self.__is_reference_only = is_reference_only
    self.__borrowed = borrowed
    self.__due_date = due_date
    self.__price = price
    self.__status = status
    self.__date_of_purchase = date_of_purchase
    self.__publication_date = publication_date
    self.__placed_at = placed_at

  def checkout(self, member_id):
    None


class Rack:
  def __init__(self, number, location_identifier):
    self.__number = number
    self.__location_identifier = location_identifier
    
    The Book, BookItem and Rack classes
```

```c++
// User is an abstract class
class Book {
    private: 
        string isbn;
        string title;
        string subject;
        string publisher;
        string language;
        int numberOfPages;
        BookFormat bookFormat;
        list<Author> authors;
};
 
class BookItem : public Book {
    private: 
        string id;
        bool isReferenceOnly;
        time_t borrowed;
        Date dueDate;
        double price;
        BookStatus status;
        time_t dateOfPurchase;
        time_t publicationDate;
        Rack placedAt;

    public: 
        bool checkout(string memberId);
};

class Rack {
    private: 
        int number;
        string locationIdentifier;
};

The Book, BookItem and Rack classes
```

```javascript
class Book {
    #isbn;
    #title;
    #subject;
    #publisher;
    #language;
    #numberOfPages;
    #bookFormat;
    #authors;
    constructor(isbn, title, subject, publisher, language, numberOfPages, bookFormat) {
        this.#isbn = isbn;
        this.#title = title;
        this.#subject = subject;
        this.#publisher = publisher;
        this.#language = language;
        this.#numberOfPages = numberOfPages;
        this.#bookFormat = bookFormat;
        this.#authors = new Array();
    }
}

class BookItem extends Book {
    #barcode;
    #isReferenceOnly;
    #borrowed;
    #dueDate;
    #price;
    #status;
    #dateOfPurchase;
    #publicationDate;
    #placedAt;

    constructor(barcode, isReferenceOnly, borrowed, dueDate, price, status, dateOfPurchase, publicationDate, placedAt) {
        this.#barcode = barcode;
        this.#isReferenceOnly = isReferenceOnly;
        this.#borrowed = borrowed;
        this.#dueDate = dueDate;
        this.#price = price;
        this.#status = status;
        this.#dateOfPurchase = dateOfPurchase;
        this.#placedAt = placedAt;
    }

    checkout(memberId);
}

class Rack {
    #number;
    #locationIdentifier

    constructor(number, locationIdentifier) {
        this.#number = number;
        this.#locationIdentifier = locationIdentifier;
    }
}

The Book, BookItem and Rack classes
```

### Notification
The Notification class is another abstract class responsible for sending notifications to the users, with the PostalNotification and EmailNotification classes as its child classes. The implementation of this class can be found below:

```java
// User is an abstract class
public abstract class Notification {
    Private String notificationId;
    Private Date creationDate;
    Private String content;

    public abstract boolean sendNotification();
}

public class PostalNotification extends Notification {
    private Address address;

    public boolean sendNotification(){
        // definition
    }
}

public class EmailNotification extends Notification {
    private String email;

    public boolean sendNotification(){
        // definition
    }
}

Notification and its derived classes

```

```c#
// User is an abstract class
abstract class Notification {
    Private String notificationId;
    Private DateTime creationDate;
    Private String content;

    public abstract bool SendNotification();
}

class PostalNotification : Notification {
    private Address address;

    public override bool sendNotification(){
        // definition
    }
}

class EmailNotification : Notification {
    private String email;

    public override bool sendNotification(){
        // definition
    }
}

Notification and its derived classes

```

```python
# User is an abstract class
from abc import ABC, abstractmethod

class Notification(ABC)):
  def __init__(self, notification_id, creation_date, content):
    self.__notification_id = notification_id
    self.__creation_date = creation_date
    self.__content = content

  def send_notification(self):
    None

class PostalNotification(Notification):
  def __init__(self, notification_id, creation_date, content, address):
    super().__init__(notification_id, creation_date, content)
    self.__address = address

class EmailNotification(Notification):
  def __init__(self, notification_id, creation_date, content, email):
    super().__init__(notification_id, creation_date, content)
    self.__email = email
    
    Notification and its derived classes

```

```c++
// User is an abstract class
class Notification {
    private: 
        string notificationId;
        time_t creationDate;
        string content;

    public:
        virtual bool sendNotification() = 0;
};

class PostalNotification : public Notification {
    private: 
        Address address;

    public:
        bool sendNotification(){
            //definition
        }
};

class EmailNotification : public Notification {
    private: 
        string email;

    public:
        bool sendNotification(){
            //definition
        }
};

Notification and its derived classes

```

```javascript
class Notification {
    #notificationId;
    #creatioDate;
    #content;
    constructor() {
        if (this.constructor == Notification) {
            throw new Error("Abstract classes can't be instantiated.");
        }
    }

    sendNotification();
}

class PostalNotification extends Notification {
    #address;

    constructor(notificationId, creationDate, content, address) {
        this.#notificationId = notificationId;
        this.#creationDate = creationDate;
        this.#content = content;
        this.#address = address;
    }
}

class EmailNotification extends Notification {
    #email;

    constructor(notificationId, creationDate, content, email) {
        this.#notificationId = notificationId;
        this.#creationDate = creationDate;
        this.#content = content;
        this.#email = email;
    }
}

Notification and its derived classes

```
### Search and catalog
The Search is an interface used in the efficient searching of library books by various methods, and the Catalog class is used to implement the search interface to help in book searching. The code to perform this functionality is presented below:

The Search is an interface used in the efficient searching of library books by various methods, and the Catalog class is used to implement the search interface to help in book searching. The code to perform this functionality is presented below:

```java
public interface Search {
    // Interface method (does not have a body)
    public List<Book> searchByTitle(String title);
    public List<Book> searchByAuthor(String author);
    public List<Book> searchBySubject(String subject);
    public List<Book> searchByPublicationDate(Date publishDate);
}

public class Catalog implements Search {
    private HashMap<String, List<Book>> bookTitles;
    private HashMap<String, List<Book>> bookAuthors;
    private HashMap<String, List<Book>> bookSubjects;
    private HashMap<String, List<Book>> bookPublicationDates;

    public List<Book> searchByTitle(String query) {
        // definition
    }
    public List<Book> searchByAuthor(String query) {
        // definition
    }
    public List<Book> searchBySubject(String query) {
        // definition
    }
    public List<Book> searchByPublicationDate(String query) {
        // definition
    }
}

       The Search interface and the Catalog class

```

```c#
public interface ISearch {
    // Interface method (does not have a body)
    public List<Book> SearchByTitle(String title);
    public List<Book> SearchByAuthor(String author);
    public List<Book> SearchBySubject(String subject);
    public List<Book> SearchByPublicationDate(DateTime date);
}

public class Catalog : ISearch {
    private HashMap<String, List<Book>> bookTitles;
    private HashMap<String, List<Book>> bookAuthors;
    private HashMap<String, List<Book>> bookSubjects;
    private HashMap<String, List<Book>> bookPublicationDates;

    public List<Book> SearchByTitle(String title) {
        // definition
    }
    public List<Book> SearchByAuthor(String author) {
        // definition
    }
    public List<Book> SearchBySubject(String subject) {
        // definition
    }
    public List<Book> SearchByPublicationDate(DateTime date) {
        // definition
    }
}
           The Search interface and the Catalog class

```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_by_title(self, title):
    None

  def search_by_author(self, author):
    None

  def search_by_subject(self, subject):
    None

  def search_by_publication_date(self, publish_date):
    None


class Catalog(Search):
  def __init__(self):
    self.__book_titles = {}
    self.__book_authors = {}
    self.__book_subjects = {}
    self.__book_publication_dates = {}

  def search_by_title(self, title):
    None

  def search_by_author(self, author):
    None

  def search_by_subject(self, subject):
    None

  def search_by_publication_date(self, publish_date):
    None
    
           The Search interface and the Catalog class
```

```c++
class Search {
    public: 
        searchByTitle(string title) = 0;
        searchByAuthor(string author) = 0;
        searchBySubject(string subject) = 0;
        searchByPublicationDate(time_t publishDate) = 0;
};

class Catalog : public Search {
    private:
        map<string, list<Book>> bookTitles;
        map<string, list<Book>> bookAuthors;
        map<string, list<Book>> bookSubjects;
        map<string, list<Book>> bookPublicationDates;

    public:
        searchByTitle(string title) {
            // definition
        }
        searchByAuthor(string author) {
            // definition
        }
        searchBySubject(string subject) {
            // definition
        }
        searchByPublicationDate(time_t publishDate) {
            // definition
        }
};

              The Search interface and the Catalog class
```

```javascript
class Search {
    searchByTitle(title);
    searchByAuthor(author);
    searchBySubject(subject);
    searchByPublicationDate(publishDate);
}

class Catalog extends Search {
    #bookTitles;
    #bookAuthors;
    #bookSubjects;
    #bookPublicationDates;

    constructor(){
        this.bookTitles = new Map();
        this.bookAuthors = new Map();
        this.bookSubjects = new Map();
        this.bookPublicationDates = new Map();
    }
    searchByTitle(title);
    searchByAuthor(author);
    searchBySubject(subject);
    searchByPublicationDate(publishDate);
}
           The Search interface and the Catalog class
```

### Library
The final class of LMS is the Library class which will be a Singleton class, meaning the entire system will have only one instance of this class. The implementation of this class can be found below:

```java
public class Library {
    private String name;
    private Address address;

    public Address getAddress();

    // The Library is a singleton class that ensures it will have only one active instance at a time
    private static Library library = null;
    
    // Created a static method to access the singleton instance of Library class
    public static Library getInstance() {
        if (library == null) {
            library = new Library();
        }
        return library;
    }
}

         The Library class

```

```c#
class Library {
    private String name;
    private Address address;

    public Address GetAddress();

    // The Library is a singleton class that ensures it will have only one active instance at a time
    private static Library library = null;

    // Created a static method to access the singleton instance of Library
    public static Library GetInstance {
        get {
            if (library == null) {
                library = new Library();
            }
            return library;
        }
    }
}
      
      The Library class

```

```python
# The Library is a singleton class that ensures it will have only one active instance at a time

class __Library(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__Library, cls).__new__(cls)
    return cls.__instances

class Library(metaclass = __Library):
  def __init__(self, id, name, address):
    self.__name = name
    self.__address = address
    self.__parking_rate = parking_rate

  def get_address(self):
    None
    
    The Library class

```

```c++
class Library {
    private: 
        string name;
        Address address;

        // The Library is a singleton class that ensures it will have only one active instance at a time
        static Library library = NULL;

    public:
        Address getAddress();
        // Created a static method to access the singleton instance of Library
        static Library getInstance() {
            if (library == NULL) {
            library = new Library();
            }
            return library;
        }
};

         The Library class

```

```javascript
class Library {
    #name;
    #address;

    getAddress();

    constructor(name, address) {
        this.name = name;
        this.address = address;
        
        // The Library is a singleton class that ensures it will have only one active instance at a time
        var library = null;
    }

    // Created a static method to access the singleton instance of Library
    getInstance() {
        if (library == null) {
            library = new Library;
        }
        return library;
    }
}

           The Library class

```
    
## Wrapping up
We've explored the complete design of a library management system in this chapter. We've looked at how a basic library management system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
