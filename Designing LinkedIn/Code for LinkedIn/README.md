# Code for LinkedIn
We've gone over the different aspects of LinkedIn and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the LinkedIn network using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in LinkedIn:

- Java

- C#

- Python

- C++

- JavaScript

## LinkedIn classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Constants
The following code provides the definition of the various enums and custom data types being used in the LinkedIn design:
```
Note: JavaScript does not support enumerations so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
public class Address {
  private int zipCode;
  private String streetAddress;
  private String city;
  private String state;
  private String country;
}

enum AccountStatus {
  ACTIVE,
  DEACTIVATED,
  BLOCKED,
  DELETED
}

enum ConnectionInviteStatus {
  PENDING, 
  ACCEPTED,
  IGNORED
}

enum JobStatus {
  OPEN,
  ON_HOLD,
  CLOSED
}
```

```c#
class Address {
  private int zipCode;
  private string streetAddress;
  private string city;
  private string state;
  private string country;
}

enum AccountStatus {
  ACTIVE,
  DEACTIVATED,
  BLOCKED,
  DELETED
}

enum ConnectionInviteStatus {
  PENDING, 
  ACCEPTED, 
  IGNORED
}

enum JobStatus {
  OPEN,
  ON_HOLD,
  CLOSED
}
```

```python
class Address:
  def __init__(self, zip_code, street_address, city, state, country):
    self.__zip_code = zip_code
    self.__street_address = street_address
    self.__city = city
    self.__state = state
    self.__country = country

class AccountStatus(enum.Enum):
  ACTIVE = 1 
  DEACTIVATED = 2
  BLOCKED = 3
  DELETED = 4

class ConnectionInviteStatus(enum.Enum):
  PENDING = 1 
  ACCEPTED = 2
  IGNORED = 3

class JobStatus(enum.Enum):
  OPEN = 1 
  ON_HOLD = 2
  CLOSED = 3
```

```c++
class Address {
  private:
    int zipCode;
    string streetAddress;
    string city;
    string state;
    string country;
};

enum AccountStatus {
  ACTIVE,
  DEACTIVATED,
  BLOCKED,
  DELETED
};

enum ConnectionInviteStatus {
  PENDING, 
  ACCEPTED, 
  IGNORED
};

enum JobStatus {
  OPEN,
  ON_HOLD,
  CLOSED
};
```

```javascript
class Address {
  #zipCode
  #streetAddress
  #city
  #state
  #country

  constructor(zipCode, streetAddress, city, state, country) {
    this.#zipCode = zipCode
    this.#streetAddress = streetAddress
    this.#city = city
    this.#state = state
    this.#country = country
  }
}

const AccountStatus = Object.freeze({
  ACTIVE,
  DEACTIVATED,
  BLOCKED,
  DELETED
});

const ConnectionInviteStatus = Object.freeze({
  PENDING, 
  ACCEPTED, 
  IGNORED
});

const JobStatus = Object.freeze({
  OPEN,
  ON_HOLD,
  CLOSED
});
```
### Account
The Account class refers to an account of a user on LinkedIn. It includes their personal details, such as username, password, etc. It also allows users to reset their existing passwords. The definition of this class is given below:

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
};
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

### Person, admin, and user
The Person class is an abstract class and contains details like the name, address, phone number, and email. It is derived into the Admin and User class.

```java
// Person will be an abstract class
public abstract class Person {
  private String name;
  private Address address;
  private String email;
  private String phone;
  private Account account;
}

public class Admin extends Person {
  public boolean blockUser(User user);
  public boolean unblockUser(User user);
  public boolean disablePage(CompanyPage page);
  public boolean enablePage(CompanyPage page);
  public boolean deleteGroup(Group group);
}

public class User extends Person {
  private int userId;
  private Date dateOfJoining;
  private Profile profile;
  private List<User> connections;
  private List<User> followsUsers;
  private List<CompanyPage> followCompanies;
  private List<Group> joinedGroups;
  private List<CompanyPage> createdPages;
  private List<Group> createdGroups;

  public boolean sendMessage(Message message);
  public boolean sendInvite(ConnectionInvitation invite);
  public boolean cancelInvite(ConnectionInvitation invite);
  public boolean createPage(CompanyPage page);
  public boolean deletePage(CompanyPage page);
  public boolean createGroup(Group group);
  public boolean deleteGroup(Group group);
  public boolean createPost(Post post);
  public boolean deletePost(Post post);
  public boolean createComment(Comment comment);
  public boolean deleteComment(Comment comment);
  public boolean react(Post post);
  public boolean requestRecommendation(User user);
  public boolean acceptRecommendation(User user);
  public boolean applyForJob(Job job);
}
```

```c#
// Person will be an abstract class
public abstract class Person {
  private string name;
  private Address address;
  private string email;
  private string phone;
  private Account account;
}

public class Admin : Person {
  public bool BlockUser(User user);
  public bool UnblockUser(User user);
  public bool DisablePage(CompanyPage page);
  public bool EnablePage(CompanyPage page);
  public bool DeleteGroup(Group group);
}

public class User : Person {
  private int userId;
  private DateTime dateOfJoining;
  private Profile profile;
  
  private List<User> followsUsers;
  private List<CompanyPage> followCompanies;
  private List<User> connections;
  private List<User> followsUsers;
  private List<CompanyPage> followCompanies;
  private List<Group> joinedGroups;
  private List<CompanyPage> createdPages;
  private List<Group> createdGroups;

  public bool SendMessage(Message message);
  public bool SendInvite(ConnectionInvitation invite);
  public bool CancelInvite(ConnectionInvitation invite);
  public bool CreatePage(CompanyPage page);
  public bool DeletePage(CompanyPage page);
  public bool CreateGroup(Group group);
  public bool DeleteGroup(Group group);
  public bool CreatePost(Post post);
  public bool DeletePost(Post post);
  public bool CreateComment(Comment comment);
  public bool DeleteComment(Comment comment);
  public bool React(Post post);
  public bool RequestRecommendation(User user);
  public bool AcceptRecommendation(User user);
  public bool ApplyForJob(Job job);
}
```

```python
from abc import ABC, abstractmethod

class Person(ABC):
  def __init__(self, name, address, email, phone, account):
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone = phone
    self.__account = account

#Admin extends Person
class Admin(Person):
  def __init__(self, name, address, email, phone, email):
    super().__init__(name, address, email, phone, account)
  
  def block_user(self, user):
    pass
  def unblock_user(self, user):
    pass
  def disable_page(self, page):
    pass
  def enable_page(self, page):
    pass
  def delete_group(self, group):
    pass

# User extends Person
class User(Person):
  def __init__(self, name, address, email, phone, email, user_id, date_of_joining, profile):
    self.__user_id = user_id
    self.date_of_joining = date_of_joining
    self.__profile = profile
    self.__connections = []
    self.__follows_users = []
    self.__follows_companies = []
    self.__joined_groups = []
    self.__created_pages = []
    self.__created_groups = []
    super().__init__(name, address, email, phone, account)
  
    def send_message(self, message):
      pass
    def send_invite(self, invite):
      pass
    def cancel_invite(self, invite):
      pass
    def create_page(self, page):
      pass
    def delete_page(self, page):
      pass
    def create_group(self, group):
      pass
    def delete_group(self, group):
      pass
    def create_post(self, post):
      pass
    def delete_post(self, post):
      pass
    def create_comment(self, comment):
      pass
    def delete_comment(self, comment):
      pass
    def react(self, post):
      pass
    def request_recommendation(self, user):
      pass
    def accept_recommendation(self, user):
      pass
    def apply_for_job(self, job):
      pass
```

```c++
// Person will be an abstract class
class Person {
  private:
    string name;
    Address address;
    string email;
    string phone;
    Account account;
};

class Admin : public Person {
  public:
    bool blockUser(User user);
    bool unblockUser(User user);
    bool disablePage(CompanyPage page);
    bool enablePage(CompanyPage page);
    bool deleteGroup(Group group);
};

class User : public Person {
  private:
    int userId;
    time_t dateOfJoining;
    Profile profile;
  
    vector<User> followsUsers;
    vector<CompanyPage> followCompanies;
    vector<User> connections;
    vector<User> followsUsers;
    vector<CompanyPage> followCompanies;
    vector<Group> joinedGroups;
    vector<CompanyPage> createdPages;
    vector<Group> createdGroups;

  public:
    bool sendMessage(Message message);
    bool sendInvite(ConnectionInvitation invite);
    bool cancelInvite(ConnectionInvitation invite);
    bool createPage(CompanyPage page);
    bool deletePage(CompanyPage page);
    bool createGroup(Group group);
    bool deleteGroup(Group group);
    bool createPost(Post post);
    bool deletePost(Post post);
    bool createComment(Comment comment);
    bool deleteComment(Comment comment);
    bool react(Post post);
    bool requestRecommendation(User user);
    bool acceptRecommendation(User user);
    bool applyForJob(Job job);
};
```

```javascript
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

// The Admin class extends the Person class
class Admin extends Person {
  blockUser(user) {}
  unblockUser(user){}
  disablePage(page) {}
  enablePage(page) {}
  deleteGroup(group) {}
}

//The User class extends the Person class
class User extends Person {
  #userId;
  #dateOfJoining;
  #profile;
  #connections;
  #followsUsers;
  #followsCompanies;
  #joinedGroups;
  #createdPages;
  #createdGroups;

  constructor(userId, dateOfJoining, profile) {
    this.#userId = userId;
    this.#dateOfJoining = dateOfJoining;
    this.#profile = profile;
    this.#connections = new Array();
    this.#followsUsers = new Array();
    this.#followsCompanies = new Array();
    this.#joinedGroups = new Array();
    this.#createdPages = new Array();
    this.#createdGroups = new Array();
  }

  sendMessage(message) {}
  sendInvite(invite) {}
  cancelInvite(invite) {}
  createPage(page) {}
  deletePage(page) {}
  createGroup(group) {}
  deleteGroup(group) {}
  createPost(post) {}
  deletePost(post) {}
  createComment(comment) {}
  deleteComment(comment) {}
  react(post) {}
  requestRecommendation(user) {}
  acceptRecommendation(user) {}
  applyForJob(job) {}
}
```

### Recommendation, achievement, and analytics
The Recommendation, Achievement, and Analytics classes will provide a user's personal information and make up the Profile class. The definition of these classes is given below:

```java
public class Recommendation {
  private int userId;
  private Date createdOn;
  private String description;
  private boolean isAccepted;
}

public class Achievement {
  private String title;
  private Date dateAwarded;
  private String description;
}

public class Analytics {
  private int searchAppearances;
  private int profileViews;
  private int postImpressions;
  private int totalConnections;
}
```

```c#
class Recommendation {
  private int userId;
  private DateTime createdOn;
  private string description;
  private bool isAccepted;
}

class Achievement {
  private string title;
  private DateTime dateAwarded;
  private string description;
}

class Analytics {
  private int searchAppearances;
  private int profileViews;
  private int postImpressions;
  private int totalConnections;
}
```

```python
class Recommendation:
  def __init__(self, user_id, created_on, description, is_accepted):
    self.__user_id = user_id
    self.__created_on = created_on
    self.__description = description
    self.__is_accepted = is_accepted

class Achievement:
  def __init__(self, title, date_awarded, description):
    self.__title = title
    self.__date_awarded = date_awarded
    self.__description = description


class Analytics:
  def __init__(self, search_appearances, profile_views, post_impressions, total_connections):
    self.__search_appearances = search_appearances
    self.__profile_views = profile_views
    self.__post_impressions = post_impressions
    self.__total_connections = total_connections
```

```c++
class Recommendation {
  private:
    int userId;
    time_t createdOn;
    string description;
    bool isAccepted;
};

class Achievement {
  private:
    string title;
    time_t dateAwarded;
    string description;
};

class Analytics {
  private:
    int searchAppearances;
    int profileViews;
    int postImpressions;
    int totalConnections;
};
```

```javascript
class Recommendation {
  #userId;
  #createdOn;
  #description;
  #isAccepted;
  
  constructor(userId, createdOn, description, isAccepted) {
    this.#userId = userId;
    this.#created_on = createdOn;
    this.#description = description;
    this.#isAccepted = isAccepted;
  }
}

class Achievement {
  #title;
  #dateAwarded;
  #description;
  
  constructor(title, dateAwarded, description) {
    this.#title = title;
    this.#dateAwarded = dateAwarded;
    this.#description = description;
  }
}

class Analytics {
  #searchAppearances;
  #profileViews;
  #postImpressions;
  #totalConnections;
  
  constructor(searchAppearances, profileViews, postImpressions, totalConnections) {
    this.#searchAppearances = searchAppearances;
    this.#profileViews = profileViews;
    this.#postImpressions = postImpressions;
    this.#totalConnections = totalConnections;
  }
}
```

### Profile, experience, education, and skill
The Experience, Education, and Skill classes will provide a user's personal information and make up the Profile class. The definition of these classes is given below:

```java
public class Experience {
  private String title;
  private String company;
  private Address location;
  private Date startDate;
  private Date endDate;
  private String description;
}

public class Education {
  private String school;
  private String degree;
  private Date startDate;
  private Date endDate;
  private String description;
}

public class Skill {
  private string name;
}

public class Profile {
  private String headline;
  private String about;
  private String gender;
  private List<byte> profilePicture;
  private List<byte> coverPhoto;

  private List<Experience> experiences;
  private List<Education> educations;
  private List<Skill> skills;
  private List<Achievement> achievements;
  private List<Recommendation> recommendations;
  private Analytics analytics;

  public boolean addExperience(Experience experience);
  public boolean addEducation(Education education);
  public boolean addSkill(Skill skill);
  public boolean addAchievement(Achievement achievement);
}
```

```c#
class Experience {
  private string title;
  private string company;
  private Address location;
  private DateTime startDate;
  private DateTime endDate;
  private string description;
}

class Education {
  private string school;
  private string degree;
  private DateTime startDate;
  private DateTime endDate;
  private string description;
}

class Skill {
  private string name;
}

class Profile {
  private string headline;
  private string about;
  private string gender;
  private List<byte> profilePicture;
  private List<byte> coverPhoto;

  private List<Experience> experiences;
  private List<Education> educations;
  private List<Skill> skills;
  private List<Achievement> achievements;
  private List<Recommendation> recommendations;
  private Analytics analytics;

  public bool AddExperience(Experience experience);
  public bool AddEducation(Education education);
  public bool AddSkill(Skill skill);
  public bool AddAchievement(Achievement achievement);
}
```

```python
class Experience:
  def __init__(self, title, company, location, start_date, end_date, description):
    self.__title = title
    self.__company = company
    self.__location = location
    self.__start_date = start_date
    self.__end_date = end_date
    self.__description = description

class Education:
  def __init__(self, school, degree, start_date, end_date, description):
    self.__school = school
    self.__degree = degree
    self.__start_date = start_date
    self.__end_date = end_date
    self.__description = description


class Skill:
  def __init__(self, name):
    self.__name = name

class Profile:
  def __init__(self, headline, about, gender, profile_picture, cover_photo):
    self.__headline = headline
    self.__about = about
    self.__gender = gender
    self.__profile_picture = profile_picture
    self.__cover_photo = cover_photo
    self.__experiences = []
    self.__education = []
    self.__skills = []
    self.__achievements = []
    self.__recommendations = []
    self.__analytics = Analytics(0, 0, 0, 0)
  
  def add_experience(self, experience):
    pass
  def add_education(self, education):
    pass
  def add_skill(self, skill):
    pass
  def add_achievement(self, achievement):
    pass
```

```c++
class Experience {
  private:
    string title;
    string company;
    Address location;
    time_t startDate;
    time_t endDate;
    string description;
};

class Education {
  private:
    string school;
    string degree;
    time_t startDate;
    time_t endDate;
    string description;
};

class Skill {
  private:
    string name;
};

class Profile {
  private:
    string headline;
    string about;
    string gender;
    vector<signed char> profilePicture;
    vector<signed char> coverPhoto;

    vector<Experience> experiences;
    vector<Education> educations;
    vector<Skill> skills;
    vector<Achievement> achievements;
    vector<Recommendation> recommendations;
    Analytics analytics;

  public:
    bool addExperience(Experience experience);
    bool addEducation(Education education);
    bool addSkill(Skill skill);
    bool addAchievement(Achievement achievement);
};
```

```javascript
class Experience {
  #title;
  #company;
  #location;
  #startDate;
  #endDate;
  #description;
  
  constructor(title, company, location, startDate, endDate, description) {
    this.#title = title;
    this.#company = company;
    this.#location = location;
    this.#startDate = startDate;
    this.#endDate = endDate;
    this.#description = description;
  }
}

class Education {
  #school;
  #degree;
  #startDate;
  #endDate;
  #description;
  
  constructor(school, degree, startDate, endDate, description) {
    this.#school = school;
    this.#degree = degree;
    this.#startDate = startDate;
    this.#endDate = endDate;
    this.#description = description;
  }
}

class Analytics {
  #name
  
  constructor(name) {
    this.#name = name
  }
}

class Profile {
  #headline;
  #about;
  #gender;
  #profilePicture;
  #coverPhoto;
  #analytics;
  #connections;
  #experiences;
  #education;
  #skills;
  #achievements;
  #recommendations;
  
  constructor(headline, about, gender, profilePicture, coverPhoto) {
    this.#headline = headline;
    this.#about = about;
    this.#gender = gender;
    this.#profilePicture = profilePicture;
    this.#coverPhoto = coverPhoto;

    this.#experiences = new Array();
    this.#education = new Array();
    this.#skills = new Array();
    this.#achievements = new Array();
    this.#recomendations = new Array();
    this.#analytics = Analytics(0, 0, 0, 0);
  }

  addExperience(experience) {}
  addEducation(education) {}
  addSkill(skill) {}
  addAchievement(achievement) {}
}
```

### Company, job, and group
LinkedIn users can create groups and company pages. The company page contains information about the company. The company pages will host various job postings. The Job, CompanyPage, and Group classes are shown below:

```java
public class Job {
  private int jobId;
  private String jobTitle;
  private Date dateOfPosting;
  private String description;
  private CompanyPage company;
  private String employmentType;
  private Address location;
  private JobStatus status;
}

public class CompanyPage {
  private int pageId;
  private String name;
  private String description;
  private String type;
  private int companySize;
  private User createdBy;
  private List<Job> jobs;

  public boolean createJobPosting();
  public boolean deleteJobPosting(Job job);
}

public class Group {
  private int groupId;
  private String name;
  private String description;
  private int totalMembers;
  private List<User> members;

  public boolean updateDescription();
}
```

```c#
class Job {
  private int jobId;
  private string jobTitle;
  private DateTime dateOfPosting;
  private string description;
  private CompanyPage company;
  private string employmentType;
  private Address location;
  private JobStatus status;
}

class CompanyPage {
  private int pageId;
  private string name;
  private string description;
  private string type;
  private int companySize;
  private User createdBy;
  private List<Job> jobs;
  
  public bool CreateJobPosting();
  public bool DeleteJobPosting(Job);
}

class Group {
  private int groupId;
  private string name;
  private string description;
  private int totalMembers;
  private List<User> members;

  public bool UpdateDescription();
}
```

```python
class Job:
  def __init__(self, job_id, job_title, date_of_posting, description,company , employment_type, location, status):
    self.__job_id = job_id
    self.__job_title = job_title
    self.__date_of_posting = date_of_posting
    self.__description = description
    self.__company = company
    self.__employment_type = employment_type
    self.__location = location
    self.__status = status
    
class CompanyPage:
  def __init__(self, page_id, name, description, type, company_size, created_by):
    self.__page_id = page_id
    self.__name = name
    self.__description = description
    self.__type = type
    self.__company_size = company_size
    self.__created_by = created_by
    self.__jobs = []
  
  def create_job_posting(self):
    pass
  def delete_job_posting(self, job):
    pass

class Group:
  def __init__(self, group_id, name, description, total_members, members):
    self.__group_id = group_id
    self.__name = name
    self.__description = description
    self.__total_members = total_members
    self.__members = members
  
  def update_description(self):
    pass
```

```c++
class Job {
  private: 
    int jobId;
    string jobTitle;
    time_t dateOfPosting;
    string description;
    CompanyPage company;
    string employmentType;
    Address location;
    JobStatus status;
};

class CompanyPage {
  private: 
    int pageId;
    string name;
    string description;
    string type;
    int companySize;
    User createdBy;
    vector<Job> jobs;

  public:
    bool createJobPosting();
    bool deleteJobPosting(Job job);
};

class Group {
  private: 
    int groupId;
    string name;
    string description;
    int totalMembers;
    vector<User> members;

  public: 
    bool updateDescription();
};
```

```javascript
class Job {
  #jobId;
  #jobTitle;
  #dateOfPosting;
  #description;
  #company;
  #employmentType;
  #location;
  #status;

  constructor(jobId, jobTitle, dateOfPosting, description, company, employmentType, location, status) {
    this.#jobId = jobId;
    this.#jobTitle = jobTitle;
    this.#dateOfPosting = dateOfPosting;
    this.#description = description;
    this.#comapny = company;
    this.#employmentType = employmentType;
    this.#location = location;
    this.#status = status;
  }
}

class CompanyPage {
  #pageId;
  #name;
  #description;
  #type;
  #companySize;
  #createdBy;
  #jobs;

  constructor(pageId, name, description, type, companySize, createdBy) {
    this.#pageId = pageId;
    this.#name = name;
    this.#description = description;
    this.#type = type;
    this.#companySize = companySize;
    this.#createdBy = createdBy;
    this.jobs= new Array();
  }
  createJobPosting() {}
  deleteJobPOsting(job) {}
}

class Group {
  #groupId;
  #name;
  #description;
  #totalMembers;
  #members;

  constructor(groupId, name, description, totalMembers, members) {
    this.#groupId = groupId;
    this.#name = name;
    this.#description = description;
    this.#totalMembers = totalMembers;
    this.#members = members;
  }
  updateDescription() {}
}
```

### Post, comment, message, and connection invitation
LinkedIn users can create posts and comments. They can also send messages and connection invitations to other users. The definition of Post, Comment, Message, and ConnectionInvitation classes is given below:

```java
public class Post {
  private int postId;
  private User postOwner;
  private String text;
  private List<byte> media;
  private int totalReacts;
  private int totalShares;
  private List<Comment> comments;

  public boolean updateText();
}

public class Comment {
  private int commentId;
  private User commentOwner;
  private String text;
  private int totalReacts;
  private List<Comment> comments;

  public boolean updateText();
}

public class Message {
  private int messageId;
  private User sender;
  private List<User> recipients;
  private String text;
  private List<byte> media;

  public boolean addRecipients(List<User> recipients);
}

public class ConnectionInvitation {
  private User sender;
  private User recipients;
  private Date dateCreated;
  private ConnectionInviteStatus status;

  public boolean acceptConnection();
  public boolean rejectConnection();
}
```

```c#
class Post {
  private int postId;
  private User postOwner;
  private string text;
  private List<byte> media;
  private int totalReacts;
  private int totalShares;
  private List<Comment> comments;

  public bool UpdateText();
}

class Comment {
  private int commentId;
  private User commentOwner;
  private string text;
  private int totalReacts;
  private List<Comment> comments;

  public bool UpdateText();
}

class Message {
  private int messageId;
  private User sender;
  private List<User> recipients;
  private string text;
  private List<byte> media;

  public bool AddRecipients(List<User> recipients);
}

class ConnectionInvitation {
  private User sender;
  private User recipients;
  private DateTime dateCreated;
  private ConnectionInviteStatus status;

  public boolean AcceptConnection();
  public boolean RejectConnection();
}
```

```python
class Post:
  def __init__(self, post_id, post_owner, text, media):
    self.__post_id = post_id
    self.__post_owner = post_owner
    self.__text = text
    self.__media = media
    self.__total_reacts = 0
    self.__total_shares = 0
    self.__comments = []
  
  def update_text(self):
    pass

class Comment:
  def __init__(self, comment_id, comment_owner, text):
    self.__comment_id = comment_id
    self.__comment_owner = comment_owner
    self.__text = text
    self.__total_reacts = 0
    self.__comments = []
  
  def update_text(self):
    pass

class Message:
  def __init__(self, message_id, sender, recipients, text, media):
    self.__message_id = message_id
    self.__sender = sender
    self.__recipients = recipients
    self.__text = text
    self.__media = media
  
  def add_recipients(self, recipients):
    pass

class ConnectionInvitation:
  def __init__(self, sender, recipients, date_created, status):
    self.__sender = sender
    self.__recipients = recipients
    self.__date_created = date_created
    self.__status = status
  
  def accept_connection(self):
    pass

  def reject_connection(self):
    pass

```

```c++
public class Post {
  private: 
  int postId;
  User postOwner;
  string text;
  vector<signed char> media;
  int totalReacts;
  int totalShares;
  vector<Comment> comments;

  public: 
    bool updateText();
};

public class Comment {
  private:
    int commentId;
    User commentOwner;
    string text;
    int totalReacts;
    vector<Comment> comments;

  public:
    bool updateText();
};

public class Message {
  private:
    int messageId;
    User sender;
    vector<User> recipients;
    string text;
    vector<signed char> media;

  public: 
    bool addRecipients(vector<User> recipients);
};

public class ConnectionInvitation {
  private:
    User sender;
    User recipients;
    time_t dateCreated;
    ConnectionInviteStatus status;

  public: 
    bool acceptConnection();
    bool rejectConnection();
};
```

```javascript
class Post {
  #postId;
  #postOwner;
  #text;
  #media;
  #totalReacts;
  #totalShares;
  #comments;

  constructor(postId, postOwner, text, media) {
    this.#postId = postId;
    this.#postOwner = postOwner;
    this.#text = text;
    this.#media = media;
    this.#totalReacts = 0;
    this.#totalShares = 0;
    this.#comments = new Array();
  }

  updateText() {}
}

class Comment {
  #commentId;
  #commentOwner;
  #text;
  #totalReacts;
  #comments;

  constructor(commentId, commentOwner, text) {
    this.#commentId = commentId;
    this.#commentOwner = commentOwner;
    this.#text = text;
    this.#totalReacts = 0;
    this.#comments = new Array();
  }

  updateText() {}
}

class Message {
  #messageId;
  #sender;
  #recipients;
  #text;
  #media;

  constructor(messageId, sender, recipients, text, media) {
    this.#messageId = messageId;
    this.#sender = sender;
    this.#recipients = recipients;
    this.#text = text;
    this.#media = media;
  }

  addRecipients(recipients) {}
}

class ConnectionInvitation {
  #sender;
  #recipients;
  #dateCreated;
  #status;

  constructor(sender, recipients, dateCreated, status) {
    this.#sender = sender;
    this.#recipients = recipients;
    this.#dateCreated = dateCreated;
    this.#status = status;
  }

  acceptConnection() {}
  rejectConnection() {}
}

```

### Search, catalog, and notification
The SearchCatalog class contains information on users, company pages, groups, and jobs. It also implements the Search interface class to enable the search functionality based on the given criteria (user, company page, group, and job keywords).

The Notification class is responsible for sending notifications to users about any new messages, comments, posts, or connection invitations via the built-in notification option.

The definition of these classes is given below:

```java
public interface Search {
  // Interface method (does not have a body)
  public List<User> searchUser(String name);
  public List<CompanyPage> searchCompany(String name);
  public List<Group> searchGroup(String name);
  public List<Job> searchJob(String title);
}

public class SearchCatalog implements Search {
  private HashMap<String, List<User>> users;
  private HashMap<String, List<CompanyPage>> companies;
  private HashMap<String, List<Group>> groups;
  private HashMap<String, List<Job>> jobs;

  public void addNewUser(User user);
  public void addNewCompany(CompanyPage company);
  public void addNewGroup(Group group);
  public void addNewJob(Job job);

  public List<User> searchUser(String name) {
    // functionality
  }

  public List<CompanyPage> searchCompany(String name) {
    // functionality
  }

  public List<Job> searchJobs(String title) {
    // functionality
  }

  public List<Group> searchGroups(String name) {
    // functionality
  }
}

public class Notification {
  private int notificationId;
  private Date createdOn;
  private String content;

  public boolean sendNotification(Account account);
}
```

```c#
interface Search {
  public List<User> SearchUser(string name);
  public List<CompanyPage> SearchCompany(string name);
  public List<Group> SearchGroup(string name);
  public List<Job> SearchJob(string title);
}

class SearchCatalog : Search {
  private Dictionary<string, List<User>> users;
  private Dictionary<string, List<CompanyPage>> companies;
  private Dictionary<string, List<Job>> jobs;
  private Dictionary<string, List<Group>> groups;

  public void AddNewUser(User user);
  public void AddNewCompany(CompanyPage company);
  public void AddNewJob(Job job);
  public void AddNewGroup(Group group);

  public List<User> SearchUser(string name) {
    // functionality
  }

  public List<CompanyPage> SearchCompany(string name) {
    // functionality
  }

  public List<Group> SearchGroup(string name) {
    // functionality
  }

  public List<Job> SearchJob(string title) {
    // functionality
  }
}

class Notification {
  private int notificationId;
  private DateTime createdOn;
  private string content;

  public bool SendNotification(Account account);
}
```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_user(self, name):
    pass
  def search_company(self, name):
    pass
  def search_group(self, name):
    pass
  def search_job(self, title):
    pass

class SearchCatalog(Search):
  def __init__(self):
    self.__users = {}
    self.__companies = {}
    self.__groups = {}
    self.__jobs = {}

  def add_new_user(self, user):
    pass
  def add_new_company(self, company):
    pass
  def add_new_group(self, group):
    pass
  def add_new_job(self, job):
    pass

  def search_user(self, name):
    # functionality
    pass
  def search_company(self, name):
    # functionality
    pass
  def search_group(self, name):
    # functionality
    pass
  def search_job(self, title):
    # functionality
    pass

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
class Search {
  public:
    virtual vector<User> searchUser(string name) = 0;
    virtual vector<CompanyPage> searchCompany(string name) = 0;
    virtual vector<Group> searchGroup(string name) = 0;
    virtual vector<Job> searchJob(string title) = 0;
};

class SearchCatalog : public Search {
  private:
    map<string, vector<User>> users;
    map<string, vector<CompanyPage>> companies;
    map<string, vector<Job>> jobs;
    map<string, vector<Group>> groups;

  public:
    void addNewUser(User user);
    void addNewCompany(CompanyPage company);
    void addNewGroup(Group group);
    void addNewJob(Job job);

    vector<User> searchUser(string name) {
      // functionality
    }

    vector<CompanyPage> searchCompany(string name) {
      // functionality
    }

    vector<Group> searchGroup(string name) {
      // functionality
    }

    vector<Job> searchJob(string title) {
      // functionality
    }
};

class Notification {
  private:
    int notificationId;
    time_t createdOn;
    string content;

  public:
    bool sendNotification(Account account);
};
```

```javascript
class Search {
  constructor() {
    if (this.constructor === Search) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }

  searchUser(name) {}
  searchCompany(name) {}
  searchGroup(name) {}
  searchJob(title) {}
}

class SearchCatalog extends Search {
  #users;
  #companies;
  #groups;
  #jobs;

  constructor() {
    this.#users = new Map();
    this.#companies = new Map();
    this.#groups = new Map();
    this.#jobs = new Map();
  }

  searchUser(name) {
    // functionality
  }
  searchCompany(name) {
    // functionality
  }
  searchGroup(name) {
    // functionality
  }
  searchJob(title) {
    // functionality
  }
}

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
  sendNotification(account) {}
}
```
## Wrapping up
We've explored the complete design of LinkedIn in this chapter. We've looked at how LinkedIn can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
