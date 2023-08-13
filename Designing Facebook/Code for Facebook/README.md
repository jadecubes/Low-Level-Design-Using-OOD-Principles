# Code for Facebook
We’ve reviewed different aspects of Facebook and observed the attributes attached to the problem using various UML diagrams. Let’s now explore the more practical side of things, where we will work on implementing the Facebook network using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in Facebook:

- Java

- C#

- Python

- C++

- JavaScript

## Facebook classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Constants
The following code provides the definition of the various enums and custom data types being used in the Facebook design:
```
Note: JavaScript does not support enumerations so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
public class Address {
  private int zipCode;
  private String houseNo;
  private String city;
  private String state;
  private String country;
}

enum AccountStatus {
  ACTIVE, 
  BLOCKED,
  DISABLED,
  DELETED 
}

enum FriendInviteStatus {
  PENDING, 
  ACCEPTED, 
  REJECTED, 
  CANCELED
}

enum PostPrivacySettings {
  PUBLIC, 
  FRIENDS_OF_FRIENDS, 
  ONLY_FRIENDS, 
  CUSTOM
}
```

```c#
class Address {
  private int zipCode;
  private string houseNo;
  private string city;
  private string state;
  private string country;
}

enum AccountStatus {
  ACTIVE, 
  BLOCKED,
  DISABLED, 
  DELETED
}

enum FriendInviteStatus {
  PENDING, 
  ACCEPTED, 
  REJECTED, 
  CANCELED
}

enum PostPrivacySettings {
  PUBLIC, 
  FRIENDS_OF_FRIENDS, 
  ONLY_FRIENDS, 
  CUSTOM
}
```

```python
class Address:
  def __init__(self, zip_code, house_no, city, state, country):
    self.__zip_code = zip_code
    self.__house_no = house_no
    self.__city = city
    self.__state = state
    self.__country = country

class AccountStatus(enum.Enum):
  ACTIVE = 1 
  BLOCKED = 2
  DISABLED = 3
  DELETED = 4

class FriendInviteStatus(enum.Enum):
  PENDING = 1 
  ACCEPTED = 2
  REJECTED = 3
  CANCELED = 4

class PostPrivacySettings(enum.Enum):
  PUBLIC = 1 
  FRIENDS_OF_FRIENDS = 2
  ONLY_FRIENDS = 3
  CUSTOM = 4
```

```c++
class Address {
  private:
    int zipCode;
    string houseNo;
    string city;
    string state;
    string country;
}

enum AccountStatus {
  ACTIVE, 
  BLOCKED,
  DISABLED,
  DELETED 
}

enum FriendInviteStatus {
  PENDING, 
  ACCEPTED, 
  REJECTED, 
  CANCELED
}

enum PostPrivacySettings {
  PUBLIC, 
  FRIENDS_OF_FRIENDS, 
  ONLY_FRIENDS, 
  CUSTOM
}
```

```javascript
class Address {
  #zipCode
  #houseNo
  #city
  #state
  #country

  constructor(zipCode, houseNo, city, state, country) {
    this.#zipCode = zipCode
    this.#houseNo = houseNo
    this.#city = city
    this.#state = state
    this.#country = country
  }
}

const AccountStatus = Object.freeze({
  ACTIVE, 
  BLOCKED,
  DISABLED,
  DELETED 
});

const FriendInviteStatus = Object.freeze({
  PENDING, 
  ACCEPTED, 
  REJECTED, 
  CANCELED
});

const PostPrivacySettings = Object.freeze({
  PUBLIC, 
  FRIENDS_OF_FRIENDS, 
  ONLY_FRIENDS, 
  CUSTOM
});
```

### Interfaces implemented by user
Facebook will have several interfaces that will be implemented by users and are described below:

- PageFunctionsByUser: This will define the functions that a user will perform while interacting with pages.

- GroupFunctionsByUser: This will define the functions that a user will perform while interacting with groups.

- PostFunctionsByUser: This will define the functions that a user will perform while interacting with posts.

- CommentFunctionsByUser: This will define the functions that a user will perform while interacting with comments.

The definition of all these interfaces is given below:
```java
public interface PageFunctionsByUser {
  public Page createPage(String name);
  public Page sharePage(Page page);
  public void likePage(Page page);
  public void followPage(Page page);
  public void unLikePage(Page page);
  public void unFollowPage(Page page);
}

public interface GroupFunctionsByUser {
  public Group createGroup(String name);
  public void joinGroup(Group group);
  public void leaveGroup(Group group);
  public void sendGroupInvite(Group group);
}

public interface PostFunctionsByUser {
  public Post createPost(String content);
  public Post sharePost(Post post);
  public void commentOnPost(Post post);
  public void likePost(Post post);
}

public interface CommentFunctionsByUser {
  public Comment createComment(Post post, String content);
  public void likeComment(Comment comment);
}
```

```c#
interface IPageFunctionsByUser {
  public Page CreatePage(string name);
  public Page SharePage(Page page);
  public void LikePage(Page page);
  public void FollowPage(Page page);
  public void UnLikePage(Page page);
  public void UnFollowPage(Page page);
}

interface IGroupFunctions {
  public void AddUser(User user);
  public void DeleteUser(User user);
  public bool NotifyUser(User user);

  public Group CreateGroup(string name);
  public void JoinGroup(Group group);
  public void LeaveGroup(Group group);
  public void SendGroupInvite(Group group);
}

interface IPostFunctionsByUser {
  public Post CreatePost(string content);
  public Post SharePost(Post post);
  public void CommentOnPost(Post post);
  public void LikePost(Post post);
}

interface ICommentFunctionsByUser {
  public Comment CreateComment(Post post, string content);
  public void LikeComment(Comment comment);
}
```

```python
from abc import ABC, abstractmethod
class PageFunctionsByUser(ABC):
  def create_page(self, name):
    pass
  def share_page(self, page):
    pass
  def like_page(self, page):
    pass
  def follow_page(self, page):
    pass
  def unLike_page(self, page):
    pass
  def unFollow_page(self, page):
    pass

class GroupFunctions(ABC):
  def add_user(self, user):
    pass
  def delete_user(self, user):
    pass
  def notify_user(self, user):
    pass

  def create_group(self, name):
    pass
  def join_group(self, group):
    pass
  def leave_group(self, group):
    pass
  def send_group_invite(self, group):
    pass

class PostFunctionsByUser(ABC):
  def create_post(self, content):
    pass
  def share_post(self, post):
    pass
  def comment_on_post(self, post):
    pass
  def like_post(self, post):
    pass

class CommentFunctionsByUser(ABC):
  def create_comment(self, post, content):
    pass
  def like_comment(self, comment):
    pass
```

```c++
class PageFunctionsByUser {
  public: 
    virtual Page createPage(string name) = 0;
    virtual Page sharePage(Page page) = 0;
    virtual void likePage(Page page) = 0;
    virtual void followPage(Page page) = 0;
    virtual void unLikePage(Page page) = 0;
    virtual void unFollowPage(Page page) = 0;
}

interface GroupFunctions {
  public:
    virtual void addUser(User user) = 0;
    virtual void deleteUser(User user) = 0;
    virtual bool notifyUser(User user) = 0;

    virtual Group createGroup(string name) = 0;
    virtual void joinGroup(Group group) = 0;
    virtual void leaveGroup(Group group) = 0;
    virtual void sendGroupInvite(Group group) = 0;
}

interface PostFunctionsByUser {
  public: 
    virtual Post createPost(string content) = 0;
    virtual Post sharePost(Post post) = 0;
    virtual void commentOnPost(Post post) = 0;
    virtual void likePost(Post post) = 0;
}

interface CommentFunctionsByUser {
  public:
    virtual Comment createComment(Post post, string content) = 0;
    virtual void likeComment(Comment comment) = 0;
}
```

```javascript
class PageFunctionsByUser {
  constructor() {
    if (this.constructor === PageFunctionsByUser) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }

  createPage(name) {}
  sharePage(page) {}
  likePage(page) {}
  followPage(page) {}
  unLikePage(page) {}
  unFollowPage(page) {}
}

class GroupFunctions{
  constructor() {
    if (this.constructor === GroupFunctionsByUser) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }

  addUser(user) {}
  deleteUser(user) {}
  notifyUser(user) {}

  createGroup(name) {}
  joinGroup(group) {}
  leaveGroup(group) {}
  sendGroupInvire(group) {}
}

class PostFunctionsByUser{
  constructor() {
    if (this.constructor === PostFunctionsByUser) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }
  
  createPost(content) {}
  sharePost(post) {}
  commentOnPost(post) {}
  likePost(post) {}
}

class CommentFunctionsByUser{
  constructor() {
    if (this.constructor === CommentFunctionsByUser) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }

  createComment(post, content) {}
  likeComment(comment) {}
}
```



### Account
The Account class refers to an account of a user on Facebook and is responsible for containing their personal details, such as username, password, etc. It also allows users to reset their existing passwords. The definition of this class is given below:

```java
public class Account {
  private String accountId;
  private String password;
  private String username;
  private String email;
  private AccountStatus status;

  public boolean resetPassword();
}
```

```c#
class Account {
  private string accountId;
  private string password;
  private string username;
  private string email;
  private AccountStatus status;

  public bool ResetPassword();
}
```

```python
class Account:
  def __init__(self, account_id, password, username, email, status):
    self.__account_id = account_id
    self.__password = password
    self.__username = username
    self.__email = email
    self.__status = status # Refers to the AccountStatus enum

  def reset_password(self):
    pass
```

```c++
class Account {
  private: 
    string accountId;
    string password;
    string username;
    string email;
    AccountStatus status;

  public:
    bool resetPassword();
}
```

```javascript
class Account {
  #accountId;
  #password;
  #username;
  #email;
  #status;

  constructor(accountId, password, username, email, status) {
    this.#accountId = accountId;
    this.#password = password;
    this.#username = username;
    this.#email = email;
    this.#status = status; // Refers to the AccountStatus enum
  }

  resetPassword();
}
```
### Person, user, and admin
The Person class will be an abstract class that represents a normal Facebook user. A User can also be an Admin. The definition of these two classes is provided below:
```
Note: The User class will implement the interfaces mentioned above. A few of these have been mentioned in the code below.
```

```java
public class Admin {
  public void blockUser(User user);
  public void unblockUser(User user);
  public void enablePage(Page page);
  public void disablePage(Page page);
  public void deleteGroup(Group group);
  public void changeGroupPrivacy(Group group);
}

// Person will be an abstract class
public abstract class Person {
  private String name;
  private Address address;
  private String email;
  private String phone;
  private Account account;
}

// Will be using only one interface example
public class User extends Person implements PageFunctionsByUser{
  private int userId;
  private String name;
  private Date dateOfJoining;
  // The following lists contain the pages and groups that a user is admin of
  private List<Pages> pagesAdmin;
  private List<Groups> groupsAdmin;

  private Profile profile;
  public boolean sendMessage(Message message);
  public boolean sendRecommendation(Page page, Group group, User user);
  public boolean sendFriendRequest(User user);
  public boolean unfriendUser(User user);
  public boolean blockUser(User user);
  public boolean followUser(User user);

  // The functions of the different interfaces will also be present here
  public Page createPage(String name) {
    // functionality
  }
  public void likePage(Page page){
    // functionality
  }
  public void followPage(Page page){
    // functionality
  }
  public void unLikePage(Page page){
    // functionality
  }
  public void unFollowPage(Page page){
    // functionality
  }
  public Page sharePage(Page page){
    // functionality
  }
}
```

```c#
class Admin {
  public void BlockUser(User user);
  public void UnblockUser(User user);
  public void EnablePage(Page page);
  public void DisablePage(Page page);
  public void DeleteGroup(Group group);
  public void ChangeGroupPrivacy(Group group);
}

// Person will be an abstract class
public abstract class Person {
  private string name;
  private Address address;
  private string email;
  private string phone;
  private Account account;
}

// Will be using only one interface example
public class User : Person, PageFunctionsByUser {
  private int userId;
  private string name;
  private DateTime dateOfJoining;
  // The following lists contain the pages and groups that a user is admin of
  private List<Pages> pagesAdmin;
  private List<Groups> groupsAdmin;

  private Profile profile;
  public bool SendMessage(Message message);
  public bool SendRecommendation(Page page, Group group, User user);
  public bool SendFriendRequest(User user);
  public bool UnfriendUser(User user);
  public bool BlockUser(User user);
  public bool FollowUser(User user);

  // The functions of the different interfaces will also be present here
  public Page CreatePage(string name) {
    // functionality
  }
  public void LikePage(Page page) {
    // functionality
  }
  public void FollowPage(Page page) {
    // functionality
  }
  public void UnLikePage(Page page) {
    // functionality
  }
  public void UnFollowPage(Page page) {
    // functionality
  }
  public Page SharePage(Page page) {
    // functionality
  }
}
```

```python
from abc import ABC, abstractmethod

class Admin:  
  def block_user(self, user):
    pass
  def unblock_user(self, user):
    pass
  def enable_page(self, page):
    pass
  def disable_page(self, page):
    pass
  def delete_group(self, group):
    pass
  def change_group_privacy(self, group):
    pass

class Person(ABC):
  def __init__(self, name, address, email, phone, account):
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone = phone
    self.__account = account

# Will be using only one interface example
class User(Person, PageFunctionsByUser):
  def __init__(self, name, address, email, phone, account, user_id, date_of_joining, is_admin, profile):
    self.__name = name
    self.__user_id = user_id;
    self.__date_of_joining = date_of_joining
    self.__profile= profile
    # The following lists contain the pages and groups that a user is admin of
    self.__pages_admin = []
    self.__groups_admin = []    
    super().__init__(name, address, email, phone, account)
  
  def send_message(self, message):
    pass
  def send_recommendation(self, page, group, user):
    pass    
  def send_friend_request(self, user):
    pass
  def unfriend_user(self, user):
    pass
  def block_user(self, user):
    pass
  def follow_user(self, user):
    pass

  # The functions of the different interfaces will be present here
  def create_page(self, name):
    # functionality
    pass
  def like_page(self, page):
    # functionality
    pass
  def follow_page(self, page):
    # functionality
    pass
  def unLike_page(self, page):
    # functionality
    pass
  def unFollow_page(self, page):
    # functionality
    pass
  def share_page(self, page):
    # functionality
    pass
```

```c++
class Admin{
  public:
    void blockUser(User user);
    void unblockUser(User user);
    void enablePage(Page page);
    void disablePage(Page page);
    void deleteGroup(Group group);
    void changeGroupPrivacy(Group group);
}

// Person will be an abstract class
class Person {
  private: 
    string name;
    Address address;
    string email;
    string phone;
    Account account;
}

// Will be using only one interface example
class User : public Person, public PageFunctionsByUser{
  private: 
    int userId;
    string name;
    time_t dateOfJoining;
    // The following vectors contain the pages and groups that a user is admin of
    vector<Pages> pagesAdmin;
    vector<Groups> groupsAdmin;
    Profile profile;
    
  public: 
    bool sendMessage(Message message);
    bool sendRecommendation(Page page, Group group, User user);
    bool sendFriendRequest(User user);
    bool unfriendUser(User user);
    bool blockUser(User user);
    bool followUser(User user);

    // The functions of the different interfaces will be present here
    Page createPage(string name) {
      // functionality
    }
    void likePage(Page page) {
      // functionality
    }
    void followPage(Page page) {
      // functionality
    }
    void unLikePage(Page page) {
      // functionality
    }
    void unFollowPage(Page page) {
      // functionality
    }
    Page sharePage(Page page) {
      // functionality
    }
}
```

```javascript
class Admin {
  blockUser(user) {}
  unblockUser(user) {}
  enablePage(page) {}
  disablePage(page) {}
  deleteGroup(group) {}
  changeGroupPrivacy(group) {}
}

class Person {
  #name;
  #address;
  #email;
  #phone;
  #account;

  constructor(name, address, email, phone, account) {
    this.#name = name;
    this.#address = address;
    this.#email = email;
    this.#phone = phone;
    this.#account = account;
  } 
}

// JavaScript doesn't support multiple inheritances so we need to use mixins.
// Hence the functionality of this will be different from the other classes
class User extends Person {
  #userId;
  #name;
  #dateOfJoining;
  #pagesAdmin;
  #groupsAdmin;
  #profile;

  constructor(userId, name, dateOfJoining, isAdmin, profile) {
    this.#userId = userId;
    this.#name = name;
    this.#dateOfJoining = dateOfJoining;
    // The following arrays contain the pages and groups that a user is admin of
    this.#pagesAdmin = new Array();
    this.#groupsAdmin = new Array();
    this.#profile = profile;
  } 
  
  sendMessage(message) {}
  sendRecommendation(page, group, user) {}
  sendFriendRequest(user) {}
  unfriendUser(user) {}
  blockUser(user) {}
  followUser(user) {}
}
```

### Profile, education, places, and work
The Work, Education, and Places classes will provide a user's personal information and will make up the Profile class. The definition of these classes is given below:
```java
public class Profile {
  private String gender;
  private byte[] profilePicture;
  private byte[] coverPhoto;
  private List<User> friends;

  private List<int> usersFollowed;
  private List<int> pagesFollowed;
  private List<int> groupsJoined;

  private List<Work> workExperience;
  private List<Education> educationInfo;
  private List<Place> places;

  public boolean addWorkExperience(Work work);
  public boolean addEducation(Education education);
  public boolean addPlace(Place place);
  public boolean addProfilePicture(byte[] image);
  public boolean addCoverPhoto(byte[] image);
  public boolean addGender(String gender);
}

public class Work {
  private String title;
  private String company;
  private String location;
  private String description;
  private Date startDate;
  private Date endDate;
}

public class Places {
  private String name;
}

public class Education {
  private String school;
  private String degree;
  private String description;
  private Date startDate;
  private Date endDate;
}
```

```c#
class Profile {
  private string gender;
  private sbyte[] profilePicture;
  private sbyte[] coverPhoto;
  private List<User> friends;

  private List<int> usersFollowed;
  private List<int> pagesFollowed;
  private List<int> groupsJoined;

  private List<Work> workExperience;
  private List<Education> educationInfo;
  private List<Place> places;

  public bool AddWorkExperience(Work work);
  public bool AddEducation(Education education);
  public bool AddPlace(Place place);
  public bool AddProfilePicture(sbyte[] image);
  public bool AddCoverPhoto(sbyte[] image);
  public bool AddGender(string gender);
}

class Work {
  private string title;
  private string company;
  private string location;
  private string description;
  private DateTime startDate;
  private DateTime endDate;
}

class Places {
  private string name;
}

class Education {
  private string school;
  private string degree;
  private string description;
  private DateTime startDate;
  private DateTime endDate;
}
```

```python
class Profile:
  def __init__(self, gender, profile_picture, cover_photo):
    self.__gender = gender
    self.__profile_picture = profile_picture
    self.__cover_photo = cover_photo
    self.__friends = []
    self.__users_followed = [];
    self.__pages_followed = [];
    self.__groups_joined = [];
    self.__work_experience = [];
    self.__education_info = [];
    self.__places = [];

  def add_work_experience(self, work):
    pass
  def add_education(self, education):
    pass
  def add_place(self, place):
    pass
  def add_profile_picture(self, image):
    pass
  def add_cover_photo(self, image):
    pass
  def add_gender(self, gender):
    pass

class Work:
  def __init__(self, title, company, location, description, start_date, end_date):
    self.__title = title
    self.__company = company
    self.__location = location
    self.__description = description
    self.__start_date = start_date
    self.__end_date = end_date

class Places:
  def __init__(self, name):
    self.__name = name

class Education:
  def __init__(self, school, degree, description, start_date, end_date):
    self.__school = school
    self.__degree = degree
    self.__description = description
    self.__start_date = start_date
    self.__end_date = end_date
```

```c++
public class Profile {
  private:
    string gender;
    vector<signed char> profilePicture;
    vector<signed char> coverPhoto;
    vector<User> friends;

    vector<int> usersFollowed;
    vector<int> pagesFollowed;
    vector<int> groupsJoined;

    vector<Work> workExperience;
    vector<Education> educationInfo;
    vector<Place> places;

  public:
    bool addWorkExperience(Work work);
    bool addEducation(Education education);
    bool addPlace(Place place);
    bool addProfilePicture(signed char[] image);
    bool addCoverPhoto(signed char[] image);
    bool addGender(string gender);
}

public class Work {
  private: 
    string title;
    string company;
    string location;
    string description;
    time_t startDate;
    time_t endDate;
}

public class Places {
  private string name;
}

public class Education {
  private: 
    string school;
    string degree;
    string description;
    time_t startDate;
    time_t endDate;
}
```

```javascript
class Profile {
  #gender;
  #profilePicture;
  #coverPhoto;

  constructor(gender, profilePicture, coverPhoto) {
    this.#gender = gender;
    this.#profilePicture = profilePicture;
    this.#coverPhoto = coverPhoto;
    
    this.#friends = new Array();
    this.#usersFollowed = new Array();
    this.#pagesFollowed = new Array();
    this.#groupsJoined = new Array();
    this.#workExperience = new Array();
    this.#educationInfo = new Array();
    this.#places = new Array();
  }

  addWorkExperience(work) {}
  addEducation(education) {}
  addPlace(place) {}
  addProfilePicture(image) {}
  addCoverPhoto(image) {}
  addGender(gender) {}
}
 

class Work {
  #title;
  #company;
  #location;
  #description;
  #startDate;
  #endDate;

  constructor(title, company, location, description, startDate, endDate) {
    this.#title = title;
    this.#company = company;
    this.#location = location;
    this.#description = description;
    this.#startDate = startDate;
    this.#endDate = endDate;
  }
}

class Places {
  #name;

  constructor(name) {
    this.#name = name;
  }
}

class Education {
  #school;
  #degree;
  #description;
  #startDate;
  #endDate;

  constructor(school, degree, description, startDate, endDate) {
    this.#school = school;
    this.#degree = degree;
    this.#description = description;
    this.#startDate = startDate;
    this.#endDate = endDate;
  }
}
```

### Page, post, and comment
Facebook users can create and like pages, posts, and comments. The definition of these classes is given below:
```java
public class Page {
  private int pageId;
  private String name;
  private String description;
  private int likeCount;
}

public class Post {
  private int postId;
  private String content;
  private byte[] image;
  private int likeCount;
  private int shareCount;
  private User postOwner;
  private PostPrivacySettings settings;
  public changePostVisibility(Post post);
}

public class Comment {
  private int commentId;
  private String content;
  private int likeCount;
  private User commentOwner;
}
```

```c#
class Page {
  private int pageId;
  private string name;
  private string description;
  private int likeCount;
}

class Post {
  private int postId;
  private string content;
  private sbyte[] image;
  private int likeCount;
  private int shareCount;
  private User postOwner;
  private PostPrivacySettings settings;
  public ChangePostVisibility(Post post);
}

class Comment {
  private int commentId;
  private string content;
  private int likesCount;
  private User commentOwner;
}
```

```python
class Page:
  def __init__(self, page_id, description, like_count):
    self.__page_id = page_id
    self.__name = name
    self.__description = description
    self.__like_count = like_count

class Post:
  def __init__(self, post_id, content, image, like_count, share_count, post_owner, settings):
    self.__post_id = post_id
    self.__content = content
    self.__image = image
    self.__like_count = like_count
    self.__share_count = share_count
    self.__post_owner = post_owner
    self.__settings = settings # Refers to the PostPrivacySettings enum
  
  def change_post_visibility(self, post):
    pass

class Comment:
  def __init__(self, comment_id, content, like_count, comment_owner):
    self.__comment_id = comment_id
    self.__content = content
    self.__like_count = like_count
    self.__comment_owner = comment_owner
```

```c++
class Page {
  private:
    int pageId;
    string name;
    string description;
    int likeCount;
}

class Post {
  private:
    int postId;
    string content;
    signed char[] image;
    int likeCount;
    int shareCount;
    User postOwner;
    PostPrivacySettings settings;
  public changePostVisibility(Post post);
}

class Comment {
  private:
    int commentId;
    string content;
    int likeCount;
    User commentOwner;
}
```

```javascript
class Page {
  #pageId;
  #name;
  #description;
  #likeCount;

  constructor(pageId, name, description, likeCount) {
    this.#pageId = pageId;
    this.#name = name;
    this.#description = description;
    this.#likeCount = likeCount;
  }
}

class Post {
  #postId;
  #content;
  #image;
  #likeCount;
  #shareCount;
  #postOwner;
  #settings;

  constructor(postId, content, image, likeCount, shareCount, postOwner, settings) {
    this.#postId = postId;
    this.#content = content;
    this.#image = image;
    this.#likeCount = likeCount;
    this.#shareCount = shareCount;
    this.#postOwner = postOwner;
    this.#settings = settings; // Refers to the PostPrivacySettings enum
  }
  changePostVisibility(post) {}
}

class Comment {
  #commentId;
  #content;
  #likeCount;
  #commentOwner;

  constructor(commentId, content, likeCount, commentOwner) {
    this.#commentId = commentId;
    this.#content = content;
    this.#likeCount = likeCount;
    this.#commentOwner = commentOwner;
  }
}
```

### Profile privacy
Each profile will have its own privacy settings where users can change the visibility settings of their friends' list, and lock their profile and profile picture.

```java
public class ProfilePrivacy {
    public void changeFriendsListVisibility(Profile profile) {}
    public void lockProfile(Profile profile) {}
    public void lockProfilePicture(Profile profile) {}
}
```

```c#
class ProfilePrivacy {
    public void ChangeFriendsListVisibility(Profile profile) {}
    public void LockProfile(Profile profile) {}
    public void LockProfilePicture(Profile profile) {}
}
```

```python
class ProfilePrivacy:
    def change_friends_list_visibility(self, profile):
        pass
    def lock_profile(self, profile):
        pass
    def lock_profile_picture(self, profile):
        pass
```

```c++
class ProfilePrivacy {
    public:
        void changeFriendsListVisibilityProfile profile) {}
        void lockProfile(Profile profile) {}
        void lockProfilePicture(Profile profile) {}
}
```

```javascript
class ProfilePrivacy {
    changeFriendsListVisibility(profile) {}
    lockProfile(profile) {}
    lockProfilePicture(profile) {}
}
```
### Group and the group functions interface
Facebook users can also create and join groups as well as add new and delete new users. In addition, users that initially join groups will be notified of all new activities in the groups. The definition of these classes is given below:

```java
public interface GroupFunctions {
  public boolean addUser(User user);
  public boolean deleteUser(User user);
  public boolean notifyUser(User user);
}

public class Group implements GroupFunctions {
  private int groupId;
  private String name;
  private String description;
  private byte[] coverPhoto;
  private int totalUsers;
  private boolean isPrivate;
  private List<User> users;

  public boolean addUser(User user) {
    // functionality
  }
  public boolean deleteUser(User user) {
    // functionality
  }
  public boolean notifyUser(User user) {
    // functionality
  }
  public void updateDescription(String description) {}
  public void addCoverPhoto(byte[] image) {}
}
```

```c#
interface GroupFunctions {
  public bool AddUser(User user);
  public bool DeleteUser(User user);
  public bool NotifyUser(User user);
}

class Group : GroupFunctions {
  private int groupId;
  private string name;
  private string description;
  private sbyte[] coverPhoto;
  private int totalUsers;
  private bool isPrivate;
  private List<User> users;

  public bool AddUser(User user) {
    // functionality
  }
  public bool DeleteUser(User user) {
    // functionality
  }
  public bool NotifyUser(User user) {
    // functionality
  }
  public void UpdateDescription(string description) {}
  public void AddCoverPhoto(sbyte[] image) {}
}
```

```python
class GroupFunctions:
  def add_user(self, user):
    pass
  def delete_user(self, user):
    pass
  def notify_user(self, user):
    pass

class Group(GroupFunctions):
  def __init__(self, group_id, name, description, cover_photo, total_users, is_private):
    self.__group_id = group_id
    self.__name = name
    self.__description = description
    self.__cover_photo = cover_photo
    self.__total_users = total_users
    self.__is_private = is_private
    self.__users = []

  def add_user(self, user):
    # functionality
    pass

  def delete_user(self, user):
    # functionality
    pass

  def notify_user(self, user):
    # functionality
    pass

  def update_description(self, description):
    pass

  def add_cover_photo(self, image):
    pass
```

```c++
class GroupFunctions {
  public:
    virtual bool addUser(User user) = 0;
    virtual bool deleteUser(User user) = 0;
    virtual bool notifyUser(User user) = 0;
}

class Group : public GroupFunctions {
  private:
    int groupId;
    string name;
    string description;
    signed char[] coverPhoto;
    int totalUsers;
    bool isPrivate;
    vector<User> users;

  public:
    bool addUser(User user) {
      // functionality
    }
    bool deleteUser(User user) {
      // functionality
    }
    bool notifyUser(User user) {
      // functionality
    }
    void updateDescription(string description) {}
    void addCoverPhoto(signed char[] image) {}
}
```

```javascript
class GroupFunctions {
  addUser(user);
  deleteUser(user);
  notifyUser(user);
}

class Group extends GroupFunctions {
  #groupId;
  #name;
  #description;
  #coverPhoto;
  #totalUsers;
  #isPrivate;
  #users;
  
  constructor(groupId, name, description, coverPhoto, totalUsers, isPrivate) {
    this.#groupId = groupId;
    this.#name = name;
    this.#description = description;
    this.#coverPhoto = coverPhoto;
    this.#totalUsers = totalUsers;
    this.#isPrivate = isPrivate;
    this.#users = new Array();
  }

  addUser(user) {
    // functionality
  }
  deleteUser(user) {
    // functionality
  }
  notifyUser(user) {
    // functionality
  }
  updateDescription(description) {}
  addCoverPhoto(image) {}
}
```

### Message and friend request
Each Facebook user can send messages and friend requests to other users. The definition of both of these classes is given below:

```java
public class Message {
  private int messageId;
  private User sender;
  private String content;
  private List<User> recipent;
  private List<byte[]> multimedia;

  public boolean addRecipent(List<User> users);
}

public class FriendRequest {
  private User recipent;
  private User sender;
  private FriendRequestStatus status;
  private Date requestSent;
  private Date requestStatusModified;

  public boolean acceptRequest(User user);
  public boolean rejectRequest(User user);
}
```

```c#
class Message {
  private int messageId;
  private User sender;
  private string content;
  private List<User> recipent;
  private List<sbyte[]> multimedia;

  public bool AddRecipent(List<User> users);
}

class FriendRequest {
  private User recipent;
  private User sender;
  private FriendRequestStatus status;
  private DateTime requestSent;
  private DateTime requestStatusModified;

  public bool AcceptRequest(User user);
  public bool RejectRequest(User user);
}
```

```python
class Message:
  def __init__(self, message_id, sender, content, recipient, multimedia):
    self.__message_id = message_id
    self.__sender = sender
    self.__content = content
    self.__recipent = []
    self.__multimedia = []

  # user here refers to a list of users
  def add_recipent(self, user):
    pass
    
class FriendRequest:
  def __init__(self, recipent, sender, status, request_sent, request_status_modified):
    self.__recipient = recipient
    self.__sender = sender
    self.__status = status
    self.__request_sent = request_sent
    self.__request_status_modified = request_status_modified

  def accept_request(self, user):
    pass

  def reject_request(self, user):
    pass
```

```c++
class Message {
  private:
    int messageId;
    User sender;
    string content;
    vector<User> recipent;
    vector<signed char[]> multimedia;

  public bool addRecipent(vector<User> users);
}

class FriendRequest {
  private:
    User recipent;
    User sender;
    FriendRequestStatus status;
    time_t requestSent;
    time_t requestStatusModified;

  public:
    bool acceptRequest(User user);
    bool rejectRequest(User user);
}
```

```javascript
class Message {
  #messageId;
  #sender;
  #content;
  #recipent;
  #multimedia;

  constructor(messageId, sender, content, recipent, multimedia) {
    this.#messageId = messageId;
    this.#sender = sender;
    this.#content = content;
    this.#recipent = recipent;
    this.#multimedia = multimedia;
  }

  // user here refers to a list of users
  addRecipent(user) {}
}

class FriendRequest {
  #recipent;
  #sender;
  #status;
  #requestSent;
  #requestStatusModified;
  
  constructor(recipent, sender, status, requestSent, requestStatusModified) {
    this.#recipent = recipent;
    this.#sender = sender;
    this.#status = status;
    this.#requestSent = requestSent;
    this.#requestStatusModified = requestStatusModified;
  }
  
  acceptRequest(user) {}
  rejectRequest(user) {}
}
```
### Notification
The Notification class is responsible for sending notifications to users about any new messages, comments, posts, or friend requests via the built-in notification option. Its definition is given below:

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
The SearchCatalog class contains information on members, groups, pages, and various posts. It also implements the Search interface class to enable the search functionality based on the given criteria (member, group, page names, and post keywords). The definition of these two classes is given below:

```java
public interface Search {
  public List<User> searchUsers(String name);
  public List<Group> searchGroups(String name);
  public List<Page> searchPages(String name);
  public List<Post> searchPosts(String keywords);
}

public class SearchCatalog implements Search {
  HashMap<String, List<User>> userNames;
  HashMap<String, List<Group>> groupNames;
  HashMap<String, List<Page>> pageTitles;
  HashMap<String, List<Post>> posts;

  public boolean addNewUser(User user) {}
  public boolean addNewGroup(Group group) {}
  public boolean addNewPage(Page page) {}
  public boolean addNewPost(Post post) {}

  public List<User> searchUsers(String name) {
    // functionality
  }

  public List<Group> searchGroups(String name) {
    // functionality
  }

  public List<Page> searchPages(String name) {
    // functionality
  }

  public List<Post> searchPosts(String keywords) {
    // functionality
  }
}
```

```c#
interface Search {
  public List<User> SearchUsers(string name);
  public List<Group> SearchGroups(string name);
  public List<Page> SearchPages(string name);
  public List<Post> SearchPosts(string keywords);
}

class SearchCatalog : Search {
  Dictionary<string, List<User>> userNames;
  Dictionary<string, List<Group>> groupNames;
  Dictionary<string, List<Page>> pageTitles;
  Dictionary<string, List<Post>> posts;

  public bool AddNewUser(User user) {}
  public bool AddNewGroup(Group group) {}
  public bool AddNewPage(Page page) {}
  public bool AddNewPost(Post post) {}

  public List<User> SearchUsers(string name) {
    // functionality
  }

  public List<Group> SearchGroups(string name) {
    // functionality
  }

  public List<Page> SearchPages(string name) {
    // functionality
  }

  public List<Post> SearchPosts(string keywords) {
    // functionality
  }
}
```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_users(self, name):
    pass
  def search_groups(self, name):
    pass
  def search_pages(self, name):
    pass
  def search_posts(self, keywords):
    pass

class SearchCatalog(Search):
  def __init__(self):
    self.__user_names = {}
    self.__group_names = {}
    self.__page_titles = {}
    self.__posts = {}

  def add_new_user(self, user):
    pass
  def add_new_group(self, group):
    pass
  def add_new_page(self, page):
    pass
  def add_new_post(self, post):
    pass

  def search_users(self, name):
    # functionality
    pass
  def search_groups(self, name):
    # functionality
    pass
  def search_pages(self, name):
    # functionality
    pass
  def search_posts(self, keywords):
    # functionality
    pass
```

```c++
class Search {
  public:
    virtual vector<User> searchUsers(string name) = 0;
    virtual vector<Group> searchGroups(string name) = 0;
    virtual vector<Page> searchPages(string name) = 0;
    virtual vector<Post> searchPosts(string keywords) = 0;
}

class SearchCatalog : public Search {
  private:
    map<string, vector<User>> userNames;
    map<string, vector<Group>> groupNames;
    map<string, vector<Page>> pageTitles;
    map<string, vector<Post>> posts;

  public:
    bool addNewUser(User user) {}
    bool addNewGroup(Group group) {}
    bool addNewPage(Page page) {}
    bool addNewPost(Post post) {}

    vector<User> searchUsers(string name) {
      // functionality
    }

    vector<Group> searchGroups(string name) {
      // functionality
    }

    vector<Page> searchPages(string name) {
      // functionality
    }

    vector<Post> searchPosts(string keywords) {
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

  searchUsers(name) {}
  searchGroups(name) {}
  searchPages(name) {}
  searchPosts(keywords) {}
}

class SearchCatalog extends Search {
  #userNames;
  #groupNames;
  #pageTitles;
  #posts;

  constructor() {
    this.#userNames = new Map();
    this.#groupNames = new Map();
    this.#pageTitles = new Map();
    this.#posts = new Map();
  }

  searchUsers(name) {
    // functionality
  }
  searchGroups(name) {
    // functionality
  }
  searchPages(name) {
    // functionality
  }
  searchPosts(keywords) {
    // functionality
  }
}
```

## Wrapping up
We've explored the complete design of Facebook in this chapter. We've looked at how Facebook can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
