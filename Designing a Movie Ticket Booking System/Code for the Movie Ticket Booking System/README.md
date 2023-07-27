# Code for the Movie Ticket Booking System
We’ve gone over different aspects of the movie ticket booking system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the movie ticket booking system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the movie ticket booking system:

- Java

- C#

- Python

- C++

- JavaScript

## Movie ticket booking system
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations
The following code provides the definition of the various enumerations used in the movie ticket booking system:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// Enumerations
enum PaymentStatus {
  PENDING, 
  CONFIRMED, 
  DECLINED, 
  REFUNDED
}

enum BookingStatus {
  PENDING, 
  CONFIRMED, 
  CANCELLED,
  DENIED, 
  REFUNDED
}

enum SeatStatus {
  AVAILABLE,
  BOOKED,
  RESERVED
}
```

```c#
// Enumerations
enum PaymentStatus {
  PENDING, 
  CONFIRMED, 
  DECLINED, 
  REFUNDED
}

enum BookingStatus {
  PENDING, 
  CONFIRMED, 
  CANCELLED,
  DENIED, 
  REFUNDED
}

enum SeatStatus {
  AVAILABLE,
  BOOKED,
  RESERVED
}
```

```python
# Enumerations
class PaymentStatus(enum.Enum):
  PENDING = 1
  CONFIRMED = 2
  DECLINED = 3
  REFUNDED = 4

class BookingStatus(enum.Enum):
  PENDING = 1
  CONFIRMED = 2
  CANCELLED = 3
  DENIED = 4
  REFUNDED = 5

class SeatStatus(enum.Enum):
  AVAILABLE = 1
  BOOKED = 2
  RESERVED = 3
```

```c++
// Enumerations
enum PaymentStatus {
  PENDING, 
  CONFIRMED, 
  DECLINED, 
  REFUNDED
}

enum BookingStatus {
  PENDING, 
  CONFIRMED, 
  CANCELLED,
  DENIED, 
  REFUNDED
}

enum SeatStatus {
  AVAILABLE,
  BOOKED,
  RESERVED
}
```

```javascript
// Enumerations
const PaymentStatus = Object.freeze({
  PENDING, 
  CONFIRMED, 
  DECLINED, 
  REFUNDED
});

const BookingStatus = Object.freeze({
  PENDING, 
  CONFIRMED, 
  CANCELLED,
  DENIED, 
  REFUNDED
});

const SeatStatus = Object.freeze({
  AVAILABLE,
  BOOKED,
  RESERVED
});
```


### Actors
This section contains the different people that will interact with our movie ticket systems, such as a Customer, Admins, and TicketAgents. All of these classes will inherit the properties of the Person class. The definition of these classes is given below:

```java
// Person is an abstract class
public abstract class Person {
  private String name;
  private String address;
  private String phone;
  private String email;
}

public class Customer extends Person {
  private List<Bookings> bookings; // List of bookings 
  
  // booking here refers to an instance of the Booking class
  public boolean createBooking(Booking booking);
  public boolean updateBooking(Booking booking);
  public boolean deleteBooking(Booking booking);
}

public class Admin extends Person {
  // show here refers to an instance of the ShowTime class
  public boolean addShow(Show show);
  public boolean updateShow(Show show);
  public boolean deleteShow(Show show);
  public boolean addMovie(Movie movie);
  public boolean deleteMovie(Movie movie);
}

public class TicketAgent extends Person {
  // booking here refers to an instance of the Booking class
  public boolean createBooking(Booking booking);
}
```

```c#
// Person is an abstract class
public abstract class Person {
  private string name;
  private string address;
  private string phone;
  private string email;
}

class Customer : Person {
  private List<Bookings> bookings; // List of bookings

  // booking here refers to an instance of the Booking class
  public bool CreateBooking(Booking booking);
  public bool UpdateBooking(Booking booking);
  public bool DeleteBooking(Booking booking);
}

class Admin : Person {
  // show here refers to an instance of the ShowTime class
  public bool AddShow(Show show);
  public bool UpdateShow(Show show);
  public bool DeleteShow(Show show);
  public bool AddMovie(Movie movie);
  public bool DeleteMovie(Movie movie);
}

class TicketAgent : Person {
  // booking here refers to an instance of the Booking class
  public bool CreateBooking(Booking booking);
}
```

```python
from abc import ABC, abstractmethod

class Person(ABC):
  def __init__(self, name, address, phone, email):
    self.__name = name
    self.__address = address
    self.__phone = phone
    self.__email = email

class Customer(Person):
  def __init__(self, name, address, phone, email):
    self.__bookings = [] # List of bookings 
    super().__init__(name, address, phone, email)
  
  # booking here refers to an instance of the Booking class 
  def create_booking(self, booking):
    pass
  def update_booking(self, booking):
    pass
  def delete_booking(self, booking):
    pass

class Admin(Person):
  def __init__(self, name, address, phone, email):
    super().__init__(name, address, phone, email)

  # show here refers to an instance of the ShowTime class
  def add_show(self, show):
    pass
  def update_show(self, show):
    pass
  def delete_show(self, show):
    pass
  def add_movie(self, movie):
    pass
  def delete_movie(self, movie):
    pass

class TicketAgent(Person):
  def __init__(self, name, address, phone, email):
    super().__init__(name, address, phone, email)

  # booking here refers to an instance of the Booking class
  def create_booking(self, booking):
    pass
```

```c++
// Person is an abstract class
class Person {
  private:
    string name;
    string address;
    string phone;
    string email;
};

class Customer : public Person {
    private vector<Bookings> bookings; // List of bookings
    
    public:
        // booking here refers to an instance of the Booking class
        bool createBooking(Booking booking);
        bool updateBooking(Booking booking);
        bool deleteBooking(Booking booking);
};

class Admin : public Person {
    public: 
        // show here refers to an instance of the ShowTime class
        bool addShow(Show show);
        bool updateShow(Show show);
        bool deleteShow(Show show);
        bool addMovie(Movie movie);
        bool deleteMovie(Movie movie);
};

class TicketAgent : public Person {
    // booking here refers to an instance of the Booking class
    public bool createBooking(Booking booking);
};
```

```javascript
// Person is an abstract class
class Person {
  #name;
  #address;
  #email;
  #phone;

  constructor(name, address, phone, email) {
    if (this.constructor === Person) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#name = name;
      this.#address = address;
      this.#phone = phone;
      this.#email = email;
    }
  }
}

class Customer extends Person {
  constructor(name, address, phone, email) {
    this.#bookings = new Array(); // List of bookings
    super(name, address, phone, email)
  }
  
  // booking here refers to an instance of the Booking class
  createBooking(booking) {}
  updateBooking(booking) {}
  deleteBooking(booking) {}
}

class Admin extends Person {
  // show here refers to an instance of the ShowTime class
  addShow(show) {}
  updateShow(show) {}
  deleteShow(show) {}
  addMovie(movie) {}
  deleteMovie(movie) {}
}

class TicketAgent extends Person {
  // booking here refers to an instance of the Booking class
  createBooking(booking) {}
}
```

### Seat
The Seat will be an abstract class, which serves as a parent for three different types of seats: Platinum, Gold, and Silver. The definition of the Seat and its child classes is given below:

```java
// Seat is an abstract class
public abstract class Seat {
  // Data members
  private String seatNo;
  private SeatStatus status; // Refers to the SeatStatus enum

  // Member functions
  public boolean isAvailable();
  public abstract void setSeat();
  public abstract void setRate();
}

public class Platinum extends Seat {
  private double rate;
  public void setSeat() {
    // definition
  }
  public void setRate() {
    // definition
  }
}

public class Gold extends Seat {
  private double rate;
  public void setSeat() {
    // definition
  }
  public void setRate() {
    // definition
  }
}

public class Silver extends Seat {
  private double rate;
  public void setSeat() {
    // definition
  }
  public void setRate() {
    // definition
  }
}
```

```c#
// Seat is an abstract class
public abstract class Seat {
  // Data members
  private string seatNo;
  private SeatStatus status; // Refers to the SeatStatus enum
  
  // Member functions
  public bool IsAvailable();
  public abstract void SetSeat();
  public abstract void SetRate();
}

class Platinum : Seat {
  private double rate;
  public override void SetSeat() {
    // definition
  }
  public override void SetRate() {
    // definition
  }
}

class Gold : Seat {
  private double rate;
  public override void SetSeat() {
    // definition
  }
  public override void SetRate() {
    // definition
  }
}

class Silver : Seat {
  private double rate;
  public override void SetSeat() {
    // definition
  }
  public override void SetRate() {
    // definition
  }
}
```

```python
# Seat is an abstract class
from abc import ABC, abstractmethod

class Seat(ABC):
  # Data members
  def __init__(self, seat_no, status):
    self.__seat_no = seat_no
    self.__status = status # Refers to the SeatStatus enum

  # Member functions
  def is_available(self):
    pass

  @abstractmethod
  def set_seat(self):
    pass

  @abstractmethod
  def set_rate(self):
    pass

class Platinum(Seat):
  def __init__(self, seat_no, status, rate):
    self.__rate = rate
    super().__init__(seat_no, status)

  def set_seat(self):
    # functionality

  def set_rate(self):
    # functionality

class Gold(Seat):
  def __init__(self, seat_no, status, rate):
    self.__rate = rate
    super().__init__(seat_no, status)

  def set_seat(self):
    # functionality

  def set_rate(self):
    # functionality

class Silver(Seat):
  def __init__(self, seat_no, status, rate):
    self.__rate = rate
    super().__init__(seat_no, status)

  def set_seat(self):
    # functionality

  def set_rate(self):
    # functionality
```

```c++
// Seat is an abstract class
class Seat {
    // Data members
    private:
        string seatNo;
        SeatStatus status; // Refers to the SeatStatus enum

    // Member functions
    public:
        bool isAvailable(); 
        virtual void setSeat() = 0; 
        virtual void setRate() = 0; 
};

class Platinum : public Seat {
    private: 
        double rate;

    public:
        void setSeat() {
            // definition
        }
        void setRate() {
            // definition
        }
};

class Gold : public Seat {
    private:
        double rate;
    public:
        void setSeat() {
            // definition
        }
        void setRate() {
            // definition
        }
};

class Silver : public Seat {
    private:
        double rate;
    public: 
        void setSeat() {
            // definition
        }
        void setRate() {
            // definition
        }
};
```

```javascript
// Seat is an abstract class
class Seat {
  #seatNo;
  #status;

  // Data members
  constructor(seatNo, status) {
    if (this.constructor === Seat) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#seatNo = seatNo;
      this.#status = status; // Refers to the SeatStatus enum
    }
  }

  // Member functions
  isAvailable() { }
  setSeat() { }
  setRate() { }
}

class Platinum extends Seat {
  #rate;

  constructor(seatNo, status, rate) {
    this.#rate = rate;
    super(seatNo, status);
  }
  
  setSeat() {
    // functionality 
  }
  setRate() {
    // functionality 
  }
}

class Gold extends Seat {
  #rate;

  constructor(seatNo, status, rate) {
    this.#rate = rate;
    super(seatNo, status);
  }
  
  setSeat() {
    // functionality 
  }
  setRate() {
    // functionality 
  }
}

class Silver extends Seat {
  #rate;

  constructor(seatNo, status, rate) {
    this.#rate = rate;
    super(seatNo, status);
  }
  
  setSeat() {
    // functionality 
  }
  setRate() {
    // functionality 
  }
}
```

### Movie, showtime, and movie ticket
Next, we will explore the ShowTime, Movie, and MovieTicket classes that provide the details of the movie to the customer. The definition of these classes is given below:
```java
public class Movie {
  // Data members
  private String title;
  private String genre;
  private Date releaseDate;
  private String language;
  private int duration;
  private List<ShowTime> shows;
}

public class ShowTime {
  // Data members
  private int showId;
  
  // The Date datatype represents and deals with both date and time
  private Date startTime; 
  private Date date;
  private int duration;
  private List<Seat> seats;
  
  // Displays the list of available seats
  public void showAvailableSeats();
}

public class MovieTicket {
  // Data members
  private int ticketId;
  private Seat seat;
  private Movie movie;
  private ShowTime show;
}
```

```c#
class Movie {
  // Data members
  private string title;
  private string genre;
  // The DateTime datatype represents and deals with both date and time
  private DateTime releaseDate;
  private string language;
  private int duration;
  private List<ShowTime> shows;
}

class ShowTime {
  // Data members
  private int showId;

  // The DateTime datatype represents and deals with both date and time
  private DateTime startTime;
  private DateTime date;
  private int duration;
  private List<Seat> seats;

  // Displays the list of available seats
  public void ShowAvailableSeats();
}

class MovieTicket {
  // Data members
  private int ticketId;
  private Seat seat;
  private Movie movie;
  private ShowTime show;
}
```

```python
class Movie:
  # Data members
  def __init__(self, title, genre, language, release_date, duration):
    self.__title = title
    self.__genre = genre
    # release_date attribute represent date and time
    self.__release_date = release_date
    self.__language = language
    self.__duration = duration
    self.__shows = [] # List of shows

class ShowTime:
  # Data members
  def __init__(self, show_id, start_time, date, duration):
    self.__show_id = show_id
    # __start_time and __date attributes represent date and time
    self.__start_time = start_time
    self.__date = date
    self.__duration = duration
    self.__seats = [] # List of seats

  # Displays the list of available seats
  def show_available_seats():
    pass

class MovieTicket:
  # Data members
  def __init__(self, ticket_id, seat, movie, show):
    self.__ticket_id = ticket_id
    self.__seat = seat # References an instance of the Seat class
    self.__movie = movie # References an instance of the Movie class
    self.__show = show # References an instance of the ShowTime class
```

```c++
class Movie {
  // Data members
  private: 
    string title;
    string genre;
    // The time_t datatype represents and deals with both date and time
    time_t releaseDate;
    string language;
    int duration;
    vector<ShowTime> shows;
}

class ShowTime {
  // Data members
  private: 
    int showId;
    // The time_t datatype represents and deals with both date and time.
    time_t startTime;
    time_t date;
    int duration;
    vector<Seat> seats;
  
  // Displays the list of available seats
  public void showAvailableSeats();
}

class MovieTicket {
  // Date members
  private: 
    int ticketId;
    Seat seat;
    Movie movie;
    ShowTime show;
}
```

```javascript
class Movie {
  #title;
  #genre;
  #release_date;
  #language;
  #duration;

  // Data members
  constructor(title, genre, language, release_date, duration) {
    this.#title = title;
    this.#genre = genre;
    // release_date attribute represent date and time
    this.#release_date = release_date;
    this.#language = language;
    this.#duration = duration;
    this.#shows = []; // List of shows
  }
}

class ShowTime {
  #showId;
  #startTime;
  #date;
  #duration;

  // Data members
  constructor(showId, startTime, date, duration) {
    this.#showId = showId;
    // startTime and date attributes represent date and time
    this.#startTime = startTime;
    this.#date = date;
    this.#duration = duration;
    this.#seats = new Array(); // List of seats
  }

  // Displays the list of available seats
  showAvailableSeats() {}
}

class MovieTicket{
  #ticketId; 
  #seat; 
  #movie;
  #show;

  // Data members
  constructor(ticketId, seat, movie, show) {
    this.#ticketId = ticketId;
    this.#seat = seat; // References an instance of the Seat class
    this.#movie = movie; // References an instance of the Movie class
    this.#show = show; // References an instance of the ShowTime class
  }
}
```

### City, cinema, and hall
This section contains classes like Hall, Cinema, and City that make up the infrastructure of our movie ticket system. The definition of these classes is given below:

```java
public class City {
  // Data members
  private String name;
  private String state;
  private int zipCode;
  private List<Cinema> cinemas;
}

public class Cinema {
  // Data members
  private int cinemaId;
  private List<Hall> halls;
  private City city;
}

public class Hall {
  // Data members
  private int hallId;
  private List<ShowTime> shows;

  // Returns list of shows
  public List<ShowTime> findCurrentShows();
}
```

```c#
class City {
  // Data members
  private string name;
  private string state;
  private int zipCode;
  private List<Cinema> cinemas;
}

class Cinema {
  // Data members
  private int cinemaId;
  private List<Hall> halls;
  private City city;
}

class Hall {
  // Data members
  private int hallId;
  private List<ShowTime> shows;

  // Returns list of shows
  public List<ShowTime> FindCurrentShows();
}
```

```python
class City:
  # Data members
  def __init__(self, name, state, zip_code):
    self.__name = name
    self.__state = state
    self.__zip_code = zip_code
    self.__cinemas = [] # List of cinemas

class Cinema: 
  # Data members
  def __init__(self, cinema_id, city):
    self.__cinema_id = cinema_id
    self.__city = city # Refers to an instance of the City class
    self.__halls = [] # List of halls

class Hall:
  # Data members
  def __init__(self, hall_id):
    self.__hall_id = hall_id
    self.__shows = [] # List of shows

  # Returns list of shows
  def find_current_shows():
    pass
```

```c++
class City {
  // Data members
  private: 
    string name;
    string state;
    int zipCode;
    vector<Cinema> cinemas;
}

class Cinema {
  // Data members
  private: 
    int cinemaId;
    vector<Hall> halls;
    City city;
}

class Hall {
  // Data members
  private: 
    int hallId;
    vector<ShowTime> shows;

  // Returns list of shows
  public vector<ShowTime> findCurrentShows();
}
```

```javascript
class City {
  #name; 
  #state;
  #zipCode;
  #cinemas;

  // Data members
  constructor(name, state, zipCode) {
    this.#name = name;
    this.#state = state;
    this.#zipCode = zipCode; 
    this.#cinemas = new Array(); // List of cinemas
  }
}

class Cinema {
  #cinemaId;
  #city;

  // Data members
  constructor(cinemaId, city) {
    this.#cinemaId = cinemaId;
    this.#city = city;  // Refers to an instance of the City class
    this.#halls = new Array(); // List of halls
  }
}

class Hall {
  #hallID;

  // Data members
  constructor(hallId) {
    this.#hallId = hallId;
    this.#shows = new Array(); // List of shows
  }

  // Returns list of shows
  findCurrentShows() {}
}
```

### Payment
The Payment class is another abstract class, with the Cash and CreditCard classes as its child. This takes the PaymentStatus enum to keep track of the payment status. The definition of this class is given below:

```java
// Payment is an abstract class
public abstract class Payment {
  // Data members
  private double amount;

  // The Date datatype represents and deals with both date and time.
  private Date timestamp;
  private PaymentStatus status;

  public abstract boolean makePayment();
}

public class Cash extends Payment {
    public boolean makePayment() {
        // functionality
    }
}

public class CreditCard extends Payment {
    // Data members
    private String nameOnCard;
    private String cardNumber;
    private String billingAddress;
    private int code;

    public boolean makePayment() {
        // functionality
    }
}
```

```c#
// Payment is an abstract class
public abstract class Payment {
  // Data members
  private double amount;
  
  // The DateTime datatype represents and deals with both date and time.
  private DateTime timestamp;
  private PaymentStatus status;
  
  public abstract bool MakePayment();
}

class Cash : Payment {
    public override bool MakePayment() {
        // functionality
    }
}

class CreditCard : Payment {
    // Data members
    private string nameOnCard;
    private string cardNumber;
    private string billingAddress;
    private int code;
    
    public override bool MakePayment() {
        // functionality
    }
}
```

```python
# Payment is an abstract class
from abc import ABC, abstractmethod

class Payment(ABC):
  # Data members
  def __init__(self, amount, timestamp, status):
    self.__amount = amount
    self.__timestamp = timestamp
    self.__status = status # Refers to the PaymentStatus enum

  @abstractmethod
  def make_payment(self):
    pass

class Cash(Payment):
  def __init__(self, amount, timestamp, status):
    super().__init__(amount, timestamp, status)

  def make_payment(self):
    # functionality
    pass

class CreditCard(Payment):
  # Data members
  def __init__(self, amount, timestamp, status, name_on_card, card_number, billing_address, code):
    self.__name_on_card = name_on_card
    self.__card_number = card_number
    self.__billing_address = billing_address
    self.__code = code
    super().__init__(amount, timestamp, status)

  def make_payment(self):
    # functionality
    pass
```

```c++
// Payment is an abstract class
class Payment {
  // Data members
  private:
    double amount;
    // The time_t datatype represents and deals with both date and time.
    time_t timestamp;
    PaymentStatus status;

  public virtual bool makePayment() = 0;
}

class Cash : public Payment {
  public bool makePayment() {
      // functionality
  }
}

class CreditCard : public Payment {
  // Data members
  private:  
    string nameOnCard;
    string cardNumber;
    string billingAddress;
    int code;

  public bool makePayment() {
      // functionality
  }
}
```

```javascript
// Payment is an abstract class
class Payment {
    #amount;
    #timestamp;
    #status;

    // Data members
    constructor(amount, timestamp, status) {
        if (this.constructor === Payment) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#amount = amount;
            this.#timestamp = timestamp;
            this.#status = status; // Refers to the PaymentStatus enum
        }
    }

    makePayment() { }
}
class Cash extends Payment{
    makePayment(){
        // functionality
    }
}
class CreditCard extends Payment{
    #nameOnCard;
    #cardNumber;
    #billingAddress;
    #code;

    // Data members
    constructor(amount, timestamp, status, nameOnCard, cardNumber, billingAddress, code) {
        this.#nameOnCard = nameOnCard;
        this.#cardNumber = cardNumber;
        this.#billingAddress = billingAddress;
        this.#code = code;
        super(amount, timestamp, status)
    }

    makePayment(){
        // functionality
    }
}
```

### Notification
The Notification class is an abstract class that is responsible for sending notifications via email or phone/SMS after actions performed by either the admin and/or customer. Its definition is given below:

```java
// Notification is an abstract class
public abstract class Notification {
  private int notificationId;
  // The Date datatype represents and deals with both date and time.
  private Date createdOn;
  private String content;

  // person here refers to an instance of the Person class 
  public abstract void sendNotification(Person person);
}

public class EmailNotification extends Notification {
  // person here refers to an instance of the Person class 
  public void sendNotification(Person person) {
    // functionality 
  }
}

public class PhoneNotification extends Notification {
  // person here refers to an instance of the Person class 
  public void sendNotification(Person person) {
    // functionality 
  }
}
```

```c#
// Notification is an abstract class
public abstract class Notification {
  private int notificationId;
  // The DateTime datatype represents and deals with both date and time.
  private DateTime createdOn;
  private string content;

  // person here refers to an instance of the Person class 
  public abstract void SendNotification(Person person);
}

class EmailNotification : Notification {
  // person here refers to an instance of the Person class 
  public override void SendNotification(Person person) {
    // functionality 
  }
}

class PhoneNotification : Notification {
  // person here refers to an instance of the Person class 
  public override void SendNotification(Person person) {
    // functionality 
  }
}
```

```python
# Notification is an abstract class
from abc import ABC, abstractmethod

class Notification(ABC):
  def __init__(self, notification_id, created_on, content):
    self.__notification_id = notification_id
    self.__created_on = created_on
    self.__content = content

  # person here refers to an instance of the Person class 
  @abstractmethod
  def send_notification(self, person):
    pass

class EmailNotification(Notification):
  def __init__(self, notification_id, created_on, content):
    super().__init__(notification_id, created_on, content)

  # person here refers to an instance of the Person class 
  def send_notification(self, person):
    # functionality
    pass

class PhoneNotification(Notification):
  def __init__(self, notification_id, created_on, content):
    super().__init__(notification_id, created_on, content)

  # person here refers to an instance of the Person class 
  def send_notification(self, person):
    # functionality
    pass
```

```c++
// Notification is an abstract class
class Notification {
  private:
    int notificationId;
    // The time_t datatype represents and deals with both date and time.
    time_t createdOn;
    string content;

  // person here refers to an instance of the Person class 
  public virtual void sendNotification(Person person) = 0;
}

class EmailNotification : public Notification {
  // person here refers to an instance of the Person class 
  public void sendNotification(Person person) {
    // functionality 
  }
}

class PhoneNotification : public Notification {
  // person here refers to an instance of the Person class 
  public void sendNotification(Person person) {
    // functionality 
  }
}
```

```javascript
// Notification is an abstract class
class Notification {
  #notificationId;
  #createdOn;
  #content;

  constructor(notificationId, createdOn, content) {
    if (this.constructor === Notification) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#notificationId = notificationId;
      this.#createdOn = createdOn;
      this.#content = content;
    }
  }

  // person here refers to an instance of the Person class 
  sendNotification(person) {};
}

class EmailNotification extends Notification {
  // person here refers to an instance of the Person class 
  sendNotification(person) {
    // functionality 
  }
}

class PhoneNotification extends Notification {
  // person here refers to an instance of the Person class 
  sendNotification(person) {
    // functionality 
  }
}
```
### Booking
The Booking class is the main class of our movie ticket booking system and will display the information relating to a particular customer's booking. The definition of this class is given below:

```java
public class Booking {
  // Data members
  private int bookingId;
  private int amount;
  private int totalSeats;

  // The Date datatype represents and deals with both date and time.
  private Date createdOn;

  // BookingStatus enum
  private BookingStatus status;
  
  // Instances of classes
  private Payment payment;
  private ShowTime show;  
  private List<MovieTicket> tickets;
  private List<Seat> seats;
}
```

```c#
class Booking {
  // Data members
  private int bookingId;
  private int amount;
  private int totalSeats;

  // The DateTime datatype represents and deals with both date and time.
  private DateTime createdOn;

  // BookingStatus enum
  private BookingStatus status;

  // Instances of classes
  private Payment payment;
  private ShowTime show;  
  private List<MovieTicket> tickets;
  private List<Seat> seats;
}
```

```python
class Booking: 
  # Data members
  def __init__(self, booking_id, amount, total_seats, created_on, status, payment, show):
    self.__booking_id = booking_id
    self.__amount = amount
    self.__total_seats = total_seats
    self.__created_on = created_on
    self.__status = status # BookingStatus enum
    
    # Instances of classes
    self.__payment = payment
    self.__show = show
    self.__tickets = [] # List of movie tickets
    self.__seats = [] # List of seats
```

```c++
class Booking {
  // Data members
  private: 
    int bookingId;
    int amount;
    int totalSeats;
    // The time_t datatype represents and deals with both date and time.
    time_t createdOn;

    // BookingStatus enum
    BookingStatus status;

    // Instances of classes
    Payment payment;
    ShowTime show;  
    vector<MovieTicket> tickets;
    vector<Seat> seats;
}
```

```javascript
class Booking {
  #bookingId;
  #amount;
  #totalSeats;
  #createdOn;
  #isBooked;
  #payment;
  #show;

  // Data members
  constructor(bookingId, amount, totalSeats, createdOn, status, payment, show) {
    this.#bookingId = bookingId;
    this.#amount = amount;
    this.#totalSeats = totalSeats;
    this.#createdOn = createdOn;
    this.#status = status; // BookingStatus enum

    // Instances of classes
    this.#payment = payment;
    this.#show = show;
    this.#tickets = new Array(); // List of movie tickets
    this.#seats = new Array(); // List of seats
  }
}
```
### Search and catalog
The Catalog class contains the movie information and implements the Search interface class to enable the search functionality based on the given criteria (title, language, genre, and release date). The definition of these two classes is given below:

```java
public interface Search {
  public List<Movie> searchMovieTitle(String title);
  public List<Movie> searchMovieLanguage(String language);
  public List<Movie> searchMovieGenre(String genre);
  public List<Movie> searchMovieReleaseDate(Date date);
}

public class Catalog implements Search {
  HashMap<String, List<Movie>> movieTitles;
  HashMap<String, List<Movie>> movieLanguages;
  HashMap<String, List<Movie>> movieGenres;

  // The Date datatype represents and deals with both date and time.
  HashMap<Date, List<Movie>> movieReleaseDates;

  public List<Movie> searchMovieTitle(String title) {
    // functionality
  }

  public List<Movie> searchMovieLanguage(String language) {
    // functionality
  }

  public List<Movie> searchMovieGenre(String genre) {
    // functionality
  }

  public List<Movie> searchMovieReleaseDate(Date date) {
    // functionality
  }
}

```

```c#
interface ISearch {
  List<Movie> SearchMovieTitle(string title);
  List<Movie> SearchMovieLanguage(string language);
  List<Movie> SearchMovieGenre(string genre);
  List<Movie> SearchMovieReleaseDate(DateTime date);
}

class Catalogue : Search {
  Dictionary<string, List<Movie>> movieTitles;
  Dictionary<string, List<Movie>> movieLanguages;
  Dictionary<string, List<Movie>> movieGenres;
  
  // The DateTime datatype represents and deals with both date and time.
  Dictionary<DateTime, List<Movie>> movieReleaseDates;

  public List<Movie> SearchMovieTitle(string title) {
    // functionality
  }

  public List<Movie> SearchMovieLanguage(string language) {
    // functionality
  }

  public List<Movie> SearchMovieGenre(string genre) {
    // functionality
  }

  public List<Movie> SearchMovieReleaseDate(DateTime date) {
    // functionality
  }
}

```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  # Returns list of movie titles
  def search_movie_title(self, title):
    pass

  # Returns list of movie languages
  def search_movie_language(self, language):
    pass
    
  # Returns list of movie genres
  def search_movie_genre(self, genre):
    pass

  # Returns list of movie release dates
  def search_movie_release_date(self, date):
    pass


class Catalogue(Search):
  def __init__(self):
    self.__movie_titles = {}
    self.__movie_languages = {}
    self.__movie_genres = {}
    self.__movie_release_dates = {}

  # Returns list of movie titles
  def search_movie_title(self, title):
    # functionality
    pass

  # Returns list of movie languages
  def search_movie_language(self, language):
    # functionality
    pass

  # Returns list of movie genres
  def search_movie_genre(self, genre):
    # functionality
    pass

  # Returns list of movie release dates
  def search_movie_release_date(self, date):
    # functionality
    pass
```

```c++
class Search {
  public:
    virtual vector<Movie> searchMovieTitle(string title) = 0;
    virtual vector<Movie> searchMovieLanguage(string language) = 0;
    virtual vector<Movie> searchMovieGenre(string genre) = 0;
    virtual vector<Movie> searchMovieReleaseDate(time_t date) = 0;
}

class Catalogue : public Search {
  private:
    map<string, vector<Movie>> movieTitles;
    map<string, vector<Movie>> movieLanguages;
    map<string, vector<Movie>> movieGenres;
    
    // The time_t datatype represents and deals with both date and time.
    map<time_t, vector<Movie>> movieReleaseDates;

  public:
    vector<Movie> searchMovieTitle(string title) {
      // functionality
    }

    vector<Movie> searchMovieLanguage(string language) {
      // functionality
    }

    vector<Movie> searchMovieGenre(string genre) {
      // functionality
    }

    vector<Movie> searchMovieReleaseDate(time_t date) {
      // functionality
    }
}
```

```javascript
class Search {
  searchMovieTitle(title) {} // Returns list of movie titles
  searchMovieLanguage(language) {} // Returns list of movie languages
  searchMovieGenre(genre) {} // Returns list of movie genres
  searchMovieReleaseDate(date) {} // Returns list of movie release dates
}

class Catalogue extends Search {
  #movieTitles;
  #movieLanguages;
  #movieGenres;
  #movieReleaseDates;

  constructor() {
    this.#movieTitles = new Map();
    this.#movieLanguages = new Map();
    this.#movieGenres = new Map();
    this.#movieReleaseDates = new Map();
  }

  // Returns list of movie titles
  searchMovieTitle(title) {
    // functionality
  }
  // Returns list of movie languages
  searchMovieLanguage(language){
    // functionality
  }
  // Returns list of movie genres
  searchMovieGenre(genre){
    // functionality
  }
  // Returns list of movie release dates
  searchMovieReleaseDate(date){
    // functionality
  }
}
```

## Wrapping up

We've explored the complete design of a movie ticket booking system in this chapter. We've looked at how a basic movie ticket booking system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
