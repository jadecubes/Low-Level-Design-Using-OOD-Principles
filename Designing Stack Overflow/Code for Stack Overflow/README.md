# Code for Stack Overflow
We've gone over the different aspects of Stack Overflow and observed the attributes attached to the problem using various UML diagrams. Let us now explore the more practical side of things, where we will work on implementing the Stack Overflow network using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in Stack Overflow:

- Java

- C#

- Python

- C++

- JavaScript
## Stack Overflow classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Constants
The following code provides the definition of the various enums and custom data types being used in the Stack Overflow design:
```
Note: JavaScript does not support enumerations so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```
```java
enum AccountStatus {
  ACTIVE, 
  BLOCKED,
  DISABLED 
}

enum QuestionStatus {
  ACTIVE, 
  CLOSED,
  FLAGGED,
  BOUNTIED
}

enum ClosingDetail {
  COMMUNITY_SPECIFIC_REASON, 
  DUPLICATE, 
  NEEDS_CLARITY, 
  NEEDS_MORE_FOCUS,
  OPINION_BASED
}
```

```c#
enum AccountStatus {
  ACTIVE, 
  BLOCKED,
  DISABLED 
}

enum QuestionStatus {
  ACTIVE, 
  CLOSED,
  FLAGGED,
  BOUNTIED
}

enum ClosingDetail {
  COMMUNITY_SPECIFIC_REASON, 
  DUPLICATE, 
  NEEDS_CLARITY, 
  NEEDS_MORE_FOCUS,
  OPINION_BASED
}
```
```python
class AccountStatus(enum.Enum):
  ACTIVE = 1 
  BLOCKED = 2
  DISABLED = 3

class QuestionStatus(enum.Enum):
  ACTIVE = 1
  CLOSED = 2
  FLAGGED = 3
  BOUNTIED = 4

class ClosingDetail(enum.Enum):
  COMMUNITY_SPECIFIC_REASON = 1
  DUPLICATE = 2
  NEEDS_CLARITY = 3 
  NEEDS_MORE_FOCUS = 4 
  OPINION_BASED = 5
```

```c++
enum AccountStatus {
  ACTIVE, 
  BLOCKED,
  DISABLED 
}

enum QuestionStatus {
  ACTIVE, 
  CLOSED,
  FLAGGED,
  BOUNTIED
}

enum ClosingDetail {
  COMMUNITY_SPECIFIC_REASON, 
  DUPLICATE, 
  NEEDS_CLARITY, 
  NEEDS_MORE_FOCUS,
  OPINION_BASED
}
```

```javascript
const AccountStatus = Object.freeze({
  ACTIVE, 
  BLOCKED,
  DISABLED 
});

const QuestionStatus = Object.freeze({
  ACTIVE, 
  CLOSED,
  FLAGGED,
  BOUNTIED
});

const ClosingDetail = Object.freeze({
  COMMUNITY_SPECIFIC_REASON, 
  DUPLICATE, 
  NEEDS_CLARITY, 
  NEEDS_MORE_FOCUS,
  OPINION_BASED
});
```


### Account
The Account class refers to an account of a user on Stack Overflow and is responsible for containing their personal details, such as the username, password, etc. It also allows users to reset their existing passwords. The definition of this class is given below:

```java
public class Account {
  private String accountId;
  private String username;
  private String password;
  private String name;
  private String email;
  private int phone;
  private AccountStatus status;

  public boolean resetPassword();
}
```

```c#
class Account {
  private string accountId;
  private string username;
  private string password;
  private string name;
  private string email;
  private int phone;
  private AccountStatus status;

  public bool ResetPassword();
}
```

```python
class Account:
  def __init__(self, account_id, password, username, name, email, phone, status):
    self.__account_id = account_id
    self.__password = password
    self.__username = username
    self.__name = name
    self.__email = email
    self.__phone = phone
    self.__status = status # Refers to the AccountStatus enum

  def reset_password(self):
    pass
```

```c++
class Account {
  private:
    string accountId;
    string username;
    string password;
    string name;
    string email;
    int phone;
    AccountStatus status;

  public bool resetPassword();
}
```

```javascript
class Account {
  #accountId;
  #password;
  #username;
  #name;
  #email;
  #phone;
  #status;

  constructor(accountId, password, username, name, email, phone, status) {
    this.#accountId = accountId;
    this.#password = password;
    this.#username = username;
    this.#name = name;
    this.#email = email;
    this.#phone = phone;
    this.#status = status; // Refers to the AccountStatus enum
  }

  resetPassword();
}
```

### User, admin, moderator, and guest
The User class will be a parent class that represents a regular Stack Overflow user. A normal user can also be an Admin and a Moderator. Another actor is represented by the Guest class that refers to a user who can only search and view questions as well as their answers. However, they need to register an account to ask or answer questions. The definition of these classes is provided below:

```java
public class User {
  private int reputationPoints;
  private Account account;
  private List<Badge> badges;

  public boolean createQuestion(Question question);
  public boolean addAnswer(Answer answer);
  public boolean createComment(Comment comment);
  public boolean createTag(Tag tag);
  public void flagQuestion(Question question);
  public void flagAnswer(Answer answer);
  public void upvote(int id);
  public void downvote(int id);
  public void voteToCloseQuestion(Question question);
  public void voteToDeleteQuestion(Question question);
  public void acceptAnswer(Answer answer);
}

public class Admin extends User {
  public boolean blockUser(User user);
  public boolean unblockUser(User user);
  public void awardBadge(User user, Badge badge);
}

public class Moderator extends User {
  public void closeQuestion(Question question);
  public void reopenQuestion(Question question);
  public void deleteQuestion(Question question);
  public void restoreQuestion(Question question);
  public void deleteAnswer(Answer answer);
}

public class Guest {
  public void registerAccount();
}
```

```c#
public class User {
  private int reputationPoints;
  private Account account;
  private List<Badge> badges;

  public bool createQuestion(Question question);
  public bool AddAnswer(Answer answer);
  public bool CreateComment(Comment comment);
  public bool CreateTag(Tag tag);
  public void FlagQuestion(Question question);
  public void FlagAnswer(Answer answer);
  public void Upvote(int id);
  public void Downvote(int id);
  public void VoteToCloseQuestion(Question question);
  public void VoteToDeleteQuestion(Question question);
  public void AcceptAnswer(Answer answer);
}

class Admin : User {
  public bool BlockUser(User user);
  public bool UnblockUser(User user);
  public void AwardBadge(User user, Badge badge);
}

class Moderator : User {
  public void CloseQuestion(Question question);
  public void ReopenQuestion(Question question);
  public void DeleteQuestion(Question question);
  public void RestoreQuestion(Question question);
  public void DeleteAnswer(Answer answer)
}

class Guest {
  public void RegisterAccount();
}
```

```python
from abc import ABC

class User(ABC):
  def __init__(self, reputation_points, account):
    self.__reputation_points = reputation_points;
    self.__account = account;
    self.__badges = []

  def create_question(self, question):
    pass
  def add_answer(self, answer):
    pass
  def create_comment(self, comment):
    pass
  def create_tag(self, tag):
    pass
  def flag_question(self, question):
    pass
  def flag_answer(self, answer):
    pass
  def upvote(self, id):
    pass
  def downvote(self, id):
    pass
  def vote_to_close_question(self, question):
    pass
  def vote_to_delete_question(self, question):
    pass
  def accept_answer(self, answer):
    pass

class Admin(User):
  def __init__(self, reputation_points, account):
    super()__init__(reputation_points, account)

  def block_user(self, user):
    pass
  def unblock_user(self, user):
    pass
  def award_badge(self, user, badge):

class Moderator(User):
  def __init__(self, reputation_points, account):
    super()__init__(reputation_points, account)

  def close_question(self, question):
    pass
  def reopen_question(self, question):
    pass
  def delete_question(self, question):
    pass
  def restore_question(self, question):
    pass
  def delete_answer(self, answer):
    pass

class Guest:
  def register_account(self):
    pass
```

```c++
class User {
  private:
    int reputationPoints;
    Account account;
    vector<Badge> badges;

  public:
    bool createQuestion(Question question);
    bool addAnswer(Answer answer);
    bool createComment(Comment comment);
    bool createTag(Tag tag);
    void flagQuestion(Question question);
    void flagAnswer(Answer answer);
    void upvote(int id);
    void downvote(int id);
    void voteToCloseQuestion(Question question);
    void voteToDeleteQuestion(Question question);
    void acceptAnswer(Answer answer);
}

class Admin : public User {
  public:
    bool blockUser(User user);
    bool unblockUser(User user);
    void awardBadge(User user, Badge badge);
}

class Moderator : public User {
  public:
    void closeQuestion(Question question);
    void reopenQuestion(Question question);
    void deleteQuestion(Question question);
    void restoreQuestion(Question question);
    void deleteAnswer(Answer answer);
}

class Guest {
  public void registerAccount();
}
```

```javascript
class User {
  #reputationPoints;
  #account;
  #badges;

  constructor(reputationPoints, account) {
    this.#reputationPoints = reputationPoints;
    this.#account = account;
    this.#badges = new Array();
  }

  createQuestion(question);
  addAnswer(answer)
  createComment(comment);
  createTag(tag);
  flagQuestion(question);
  flagAnswer(answer);
  upvote(id);
  downvote(id);
  voteToCloseQuestion(question);
  voteToDeleteQuestion(question);
  acceptAnswer(answer);
}

class Admin extends User {
  blockUser(user);
  unblockUser(user);
  awardBadge(user, badge);
}

class Moderator extends User {
  closeQuestion(question);
  reopenQuestion(question);
  deleteQuestion(question);
  restoreQuestion(question);
  deleteAnswer(answer);
}

class Guest {
  registerAccount();
}
```

### Question, answer, comment, and bounty
Stack Overflow users can create and answer questions, upvote and downvote them, and add bounties and comments to questions. The definition of these classes is provided below:
```java
public class Question {
  private int id;
  private String title;
  private String content;
  private User createdBy;
  private int upvotes;
  private int downvotes;
  private int viewCount;
  private int score;
  private int voteCount;
  private Date creationDate;
  private Date modificationDate;
  private QuestionStatus status;
  private ClosingDetails closingReason;
  private Bounty bounty;

  private List<Tag> tags;
  private List<Comment> comments;
  private List<Answer> answers;
  private List<User> followers;

  public void addComment(Comment comment);
  public void addBounty(Bounty bounty);
}

public class Comment {
  private int id;
  private String content;
  private int flagCount;
  private int upvotes;
  private Date creationDate;
  private User postedBy;
}

public class Answer {
  private int id;
  private String content;
  private int flagCount;
  private int voteCount;
  private int upvotes;
  private int downvotes;  
  private boolean isAccepted;
  private Date creationTime;
  private User postedBy;

  private List<Comment> comments;
  private List<User> followers;

  public void addComment(Comment comment);
}

public class Bounty {
  private int reputationPoints;
  private Date expiryDate;
  public boolean updateReputationPoints(int reputation);
}
```

```c#
class Question {
  private int id;
  private string title;
  private string content;
  private User createdBy;
  private int viewCount;
  private int score;
  private int upvotes
  private int downvotes;
  private int voteCount;
  private DateTime creationDate;
  private DateTime modificationDate;
  private QuestionStatus status;
  private ClosingDetails closingReason;
  private Bounty bounty;

  private List<Tag> tags;
  private List<Comment> comments;
  private List<Answer> answers;
  private List<User> followers;

  public void AddComment(Comment comment);
  public void AddBounty(Bounty bounty);
}

class Comment {
  private int id;
  private string content;
  private int flagCount;
  private int upvotes;
  private DateTime creationDate;
  private User postedBy;
}

class Answer {
  private int id;
  private string content;
  private int flagCount;
  private int voteCount;
  private int upvotes;
  private int downvotes;  
  private bool isAccepted;
  private DateTime creationTime;
  private User postedBy;

  private List<Comment> comments;
  private List<User> followers;

  public void Upvote();
  public void Downvote();
}

class Bounty {
  private int reputationPoints;
  private DateTime expiryDate;
  public bool UpdateReputationPoints(int reputation);
}
```

```python
class Question:
  def __init__(self, id, title, content, view_count, vote_count, score, upvotes, downvotes creation_date, modification_date, status, closing_reason, created_by, bounty):
    self.__id = id
    self.__title = title
    self.__content = content
    self.__view_count = view_count
    self.__vote_count = vote_count
    self.__score = score
    self.__upvotes = upvotes
    self.__downvotes = downvotes
    self.__creation_date = creation_date
    self.__modification_date = modification_date
    self.__closing_reason = closing_reason
    self.__created_by = created_by
    self.__bounty = bounty
    
    self.__tags = []
    self.__comments = []
    self.__answers = []
    self.__followers = []
  
  def add_comment(self, comment):
    pass
  def add_bounty(self, bounty):
    pass

class Comment:
  def __init__(self, id, content, flag_count, upvotes, creation_date, user):
    self.__id = id
    self.__content = content
    self.__flag_count = flag_count
    self.__upvotes = upvotes
    self.__creation_date = creation_date
    self.__postedBy = user

class Answer:
  def __init__(self, id, content, flag_count, vote_count, upvotes, downvotes, is_available, creation_date, user):
    self.__id = id
    self.__content = content
    self.__flag_count = flag_count
    self.__vote_count = vote_count
    self.__upvotes = upvotes
    self.__downvotes = downvotes
    self.__is_accepted = is_accepted
    self.__creation_date = creation_date
    self.__postedBy = user
  
  self.__comments = []
  self.__followers = []

  def addComment(self, comment):
    pass

class Bounty:
  def __init__(self, reputation_points, expiry_date):
    self.__reputation_points = reputation_points
    self.__expiry_date = expiry_date
  
  def update_reputation_points(self, reputation):
    pass
```

```c++
class Question {
  private: 
    int id;
    string title;
    string content;
    int viewCount;
    int voteCount;
    int score;
    int upvotes;
    int downvotes;
    time_t creationDate;
    time_t modificationDate;
    QuestionStatus status;
    ClosingDetails closingReason;
    User createdBy;
    Bounty bounty;

    vector<Tag> tags;
    vector<Comment> comments;
    vector<Answer> answers;
    vector<User> followers;

  public:
    void addComment(Comment comment);
    void addBounty(Bounty bounty);
}

class Comment {
  private:
    int id;
    string content;
    int flagCount;
    int upvotes;
    time_t creationDate;
    User postedBy;
}

class Answer {
  private:
    int id;
    string content;
    int flagCount;
    int voteCount;
    int upvotes;
    int downvotes;  
    bool isAccepted;
    time_t creationTime;
    User postedBy;

    vector<Comment> comments;
    vector<User> followers;

  public:
    void addComment(Comment comment);
}

class Bounty {
  private:
    int reputationPoints;
    time_t expiryDate;

  public bool updateReputationPoints(int reputation);
}
```

```javascript
class Question {
  #id;
  #title;
  #content;
  #viewCount;
  #voteCount;
  #score;
  #upvotes
  #downvotes;
  #creationDate;
  #modificationDate;
  #status;
  #closingReason;
  #createdBy;
  #bounty;
  #tags;
  #comments;
  #answers;
  #followers;

  constructor(id, title, content, viewCount, voteCount, score, upvotes, downvotes, creationDate, modificationDate, status, closingReason, createdBy, bounty) {
    this.#id = id;
    this.#title = title;
    this.#content = content;
    this.#viewCount = viewCount;
    this.#voteCount = voteCount;
    this.#score = score;
    this.#upvotes = upvotes;
    this.#downvotes = downvotes;
    this.#creationDate = creationDate;
    this.#modificationDate = modificationDate;
    this.#createdBy = createdBy;
    this.#bounty = bounty;
    
    this.#tags = new Array();
    this.#comments = new Array();
    this.#answers = new Array();
    this.#followers = new Array();
  }

  addComment(comment) {}
  addBounty(bounty) {}
}

class Comment {
  #id;
  #content;
  #flagCount;
  #upvotes;
  #creationDate;
  #postedBy;

  constructor(id, content, flagCount, upvotes, creationDate, user) {
    this.#id = id;
    this.#content = content;
    this.#flagCount = flagCount;
    this.#upvotes = upvotes;
    this.#creationDate = creationDate;
    this.#postedBy = user;
  }
}

class Answer {
  #id;
  #content;
  #flagCount;
  #voteCount;
  #upvotes;
  #downvotes;
  #isAvailable;
  #creationDate;
  #postedBy;

  constructor(id, content, flagCount, voteCount, upvotes, downvotes, isAccepted, creationDate, user) {
    this.#id = id;
    this.#content = content;
    this.#flagCount = flagCount;
    this.#voteCount = voteCount
    this.#upvotes = upvotes;
    this.#downvotes = downvotes;
    this.#isAccepted = isAccepted;
    this.#creationDate = creationDate;
    this.#postedBy = user;

    this.#comments = new Array();
    this.#followers = new Array();
  }

  addComment(comment);
}

class Bounty {
  #reputationPoints;
  #expiryDate;

  constructor(reputationPoints, expiryDate) {
    this.#reputationPoints = reputationPoints;
    this.#expiryDate = expiryDate;
  }

  updateReputationPoints(reputation) {}
}
```


### Badge, tag, and tag list
Users can have badges that act as their reputation awards. Questions can have tags that describe the category that the question falls in. To keep a count of the tags being used, the TagList class is used. The definition of these classes can is provided below:

```java
public class Badge {
  private String name;
  private String description;
}

public class Tag {
  private String name;
  private String description;
}

public class TagList {
  private HashMap<Tag, int> tagsCount;
  public void incrementTagCount();
  public void decrementTagCount();
}
```

```c#
class Badge {
  private string name;
  private string description;
}

class Tag {
  private string name;
  private string description;
}

class TagList {
  private Dictionary<Tag, int> tagsCount;
  public void IncrementTagCount();
  public void DecrementTagCount();
}
```

```python
class Badge:
    def __init__(self, name, description):
        self.__name = name
        self.__description = description

class Tag:
    def __init__(self, name, description):
        self.__name = name
        self.__description = description

class TagList:
    def __init__(self):
        self.__tags_count = {}
    
    def increment_tag_count():
        pass
    def decrement_tag_count():
        pass
```

```c++
class Badge {
  private:
    string name;
    string description;
}

class Tag {
  private:
    string name;
    string description;
}

class TagList {
  private map<Tag, int> tagsCount;
  public:
    void incrementTagCount();
    void decrementTagCount();
}
```

```javascript
class Badge {
    #name;
    #description;

    constructor(name, description) {
        this.#name = name;
        this.#description = description;
    }
}

class Tag {
    #name;
    #description;

    constructor(name, description) {
        this.#name = name;
        this.#description = description;
    }
}

class TagList {
    #tagsCount;

    constructor() {
        this.#tagsCount = new Map();
    }
    
    incrementTagCount();
    decrementTagCount();
}
```

### Notification
The Notification class is responsible for sending notifications to users about any new messages, comments, posts, or friend requests via either a phone number, or an email. Its definition is provided below:

```java
public class Notification {
  private int notificationId;
  private Date createdOn;
  private String content;

  public boolean sendNotification(Account account);
}
```

```c#
class Notification {
  private int notificationId;
  private DateTime createdOn;
  private string content;

  public bool SendNotification(Account account);
}
```

```python
class Notification:
  def __init__(self, notification_id, created_on, content):
    self.__notification_id = notification_id
    self.__created_on = created_on
    self.__content = content

  # account here refers to the Account class
  def send_notification(self, account):
    pass
```

```c++
class Notification {
  private:
    int notificationId;
    time_t createdOn;
    string content;

  public bool sendNotification(Account account);
}
```

```javascript
class Notification {
  #notificationId;
  #createdOn;
  #content;

  constructor(notificationId, createdOn, content) {
      this.#notificationId = notificationId;
      this.#createdOn = createdOn;
      this.#content = content;
  }

  // account here refers to the Account class
  sendNotification(account) {};
}
```


### Search catalog and interface
The SearchCatalog class contains information on existing questions and answers. It also implements the Search interface class to enable the search functionality based on the given criteria (tags, usernames, and searched keywords). The definition of these two classes is provided below:

```java
public interface Search {
  public List<Question> searchByTags(String name);
  public List<Question> searchByUsers(String name);
  public List<Question> searchByWords(String words);
}

public class SearchCatalog implements Search {
  private HashMap<String, List<Tag>> questionsUsingTags;
  private HashMap<String, List<User>> questionsUsingUsers;
  private HashMap<String, List<String>> questionsUsingWords;

  public List<Question> searchByTags(String name) {
    // functionality
  }

  public List<Question> searchByUsers(String name) {
    // functionality
  }

  public List<Question> searchByWords(String words) {
    // functionality
  }
}
```

```c#
interface Search {
  public List<Question> SearchByTags(string name);
  public List<Question> SearchByUsers(string name);
  public List<Question> SearchByWords(string words);
}

class SearchCatalog : Search {
  private Dictionary<string, List<Tag>> questionsUsingTags;
  private Dictionary<string, List<User>> questionsUsingUsers;
  private Dictionary<string, List<string>> questionsUsingWords;

  public List<Question> SearchByTags(string name) {
    // functionality
  }

  public List<Question> SearchByUsers(string name) {
    // functionality
  }

  public List<Question> SearchByWords(string words) {
    // functionality
  }
}
```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_by_tags(self, name):
    pass
  def search_by_users(self, name):
    pass
  def search_by_words(self, words):
    pass

class SearchCatalog(Search):
  def __init__(self):
    self.__questions_using_tags = {}
    self.__questions_using_users = {}
    self.__questions_using_words = {}

  def search_by_tags(self, name):
    # functionality
    pass
  def search_by_users(self, name):
    # functionality
    pass
  def search_by_words(self, words):
    # functionality
    pass
```

```c++
class Search {
  public:
    virtual vector<Question> searchByTags(string name) = 0;
    virtual vector<Question> searchByUsers(string name) = 0;
    virtual vector<Question> searchByWords(string words) = 0;
}

class SearchCatalog : public Search {
  private:
    map<string, vector<Tag>> questionsUsingTags;
    map<string, vector<User>> questionsUsingUsers;
    map<string, vector<string>> questionsUsingWords;

  public:
    vector<Question> searchByTags(string name) {
      // functionality
    }

    vector<Question> searchByUsers(string name) {
      // functionality
    }

    vector<Question> searchByWords(string words) {
      // functionality
    }
}
```

```javascript
class Search {
  constructor() {
    if (this.constructor === Search) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }

  searchByTags(name) {}
  searchByUsers(name) {}
  searchByWords(words) {}
}

class SearchCatalog extends Search {
  #questionsUsingTags;
  #questionsUsingUsers;
  #questionsUsingWords;

  constructor() {
    this.#questionsUsingTags = new Map();
    this.#questionsUsingUsers = new Map();
    this.#questionsUsingWords = new Map();
  }

  searchByTags(name) {
    // functionality
  }

  searchByUsers(name) {
    // functionality
  }

  searchByWords(words) {
    // functionality
  }
}
```

## Wrapping up
We've explored the complete design of Stack Overflow in this chapter. We've looked at how Stack Overflow can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
