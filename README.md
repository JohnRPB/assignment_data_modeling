# assignment_data_modeling
Mmmmm.... dataaaaa....

*Include your ERM modeling "pseudocode" in the space below*

write down the models, columns, validations and associations you might use to implement it

1.) 

// GOALS
Students have to find courses, which consist of multiple lessons. They should be able to see attributes of courses and 
lessons too, which might have a lot of important data.

// ENTITIES
Students, Courses, Lessons, Teachers

// Attributes
Students -> FirstName, lastName, college year
Courses -> Difficulty level, subject, description, title, startDate, endDate 
Lessons -> description, title, date

// RELATIONSHIPS
Student, Course: MTM 
Course, Lesson: OTM

// DATA MODEL
To map out MTM relationships, use join tables. Student-Course join table.

2.) 

// GOALS
Be able to associate users, profiles, and the login information belonging to each. Allow multiple profiles for users, such as multiple characters per player.

// ENTITIES
Users, profiles. 

// ATTRIBUTES
Users -> firstName, lastName, city, state, country, age, gender, email 
profiles -> username, password, description, avatar

// RELATIONSHIPS
Users, Profiles: OTM

// DATA MODELS

3.) 

// GOALS
Users to be able to post links, which can be commented on by other users, and support comment nesting. Organize link order by votes.

// ENTITIES
Users, links, comments  

// ATTRIBUTES
Users -> typical stuff
link -> href, voteNumber, date, author  

// RELATIONSHIPS
Comment N, Comment N-1: OTM

// DATA MODEL
Comment hierachy is determined by injecting foreign keys for Comment type N into table for Comment type N-1, with unlimited tables, corresponding to the number of nested levels.

4.)

// GOALS


// ENTITIES
Users, links, comments  

// ATTRIBUTES
shipments: date shipped, origin, destination

// RELATIONSHIPS
simple hierarchy:
users -> orders -> shipments -> products
Users, Orders: OTM
Orders, shipments: OTM
Shipments, products: MTM

// DATA MODEL
We get quanitity of items per order by subsetting shipment table for order number (FK) and then subsetting product-shipment join table for all previously subsetted shipment IDs, and then counting rows remaining.
To handle historical user info, we include an attribute in users table for "active" vs "inactive", so a user can delete their account, but they can't delete their account's historical record in the database.









