# Reflection Questions
7.0

### 1. What was the most challenging part of building this API?

The most challenging part was connecting the API to the database and making sure that creating, reading, updating, and deleting data worked correctly. I also needed to fix errors and test the API to make sure it worked properly.

### 2. How does TypeORM make database operations easier compared to raw SQL?

TypeORM makes database operations easier because I can use TypeScript to manage database records. It reduces the need to write SQL queries manually and makes the code easier to read and maintain.

### 3. Why is it important to exclude the password field from API responses? How did you implement this?

It is important to exclude passwords because they are private information and should not be exposed to users. I can implement this by removing the password field from the user data before sending the response to the client.

### 4. Describe a scenario where you would need to use database transactions instead of individual operations.

A database transaction is useful when transferring money between two bank accounts. The withdrawal and deposit must both succeed. If one operation fails, the transaction can be rolled back to prevent incorrect data.

### 5. What is the difference between `synchronize: true` and migrations? When should you use each?

`synchronize: true` automatically updates the database structure based on the entities in the code. It is useful during development and testing. Migrations are used to manage database changes step by step. They are recommended for production because they provide better control and reduce the risk of losing data.

### 6. If you had to add a `Product` entity with a relationship to `User` (a user can have many products), how would you modify the code?

I would create a `Product` entity with fields such as `id`, `name`, and `price`. I would add a `OneToMany` relationship in the `User` entity and a `ManyToOne` relationship in the `Product` entity. This would allow one user to have many products, while each product belongs to one user.

### 7. What security improvements would you make before deploying this API to production?

Before deploying the API, I would hash passwords before storing them, add authentication and authorization, and use rate limiting to prevent too many requests. I would also validate user inputs, protect sensitive information using environment variables, enable HTTPS, and handle errors safely.# Reflection Questions
7.1
### 1. What was the most challenging part of building this API?

The most challenging part was connecting the API to the database and making sure that creating, reading, updating, and deleting data worked correctly. I also needed to fix errors and make sure the API returned the correct responses.

### 2. How does TypeORM make database operations easier compared to raw SQL?

TypeORM makes database operations easier because I can use JavaScript or TypeScript to work with database tables and records. It reduces the need to write SQL queries manually and makes the code easier to read and maintain.

### 3. Why is it important to exclude the password field from API responses? How did you implement this?

It is important to exclude passwords because they are sensitive information that should not be visible to users. I implemented this by removing the password field from the response before sending the user data to the client.

### 4. Describe a scenario where you would need to use database transactions instead of individual operations.

A transaction is useful when transferring money from one bank account to another. Both the withdrawal and deposit must succeed together. If one operation fails, the transaction should be rolled back to prevent incorrect data.

### 5. What is the difference between `synchronize: true` and migrations? When should you use each?

`synchronize: true` automatically updates the database structure based on the entities in the code. It is useful during development and testing. Migrations are changes to the database that are created and applied in a controlled way. They are better for production because they provide more control over database changes.

### 6. If you had to add a Comment entity (tasks can have many comments), how would you modify the code?

I would create a `Comment` entity with fields such as `id`, `content`, and `createdAt`. I would add a `ManyToOne` relationship in the Comment entity and a `OneToMany` relationship in the Task entity. This would allow one task to have many comments.

### 7. What security improvements would you make before deploying this API to production?

I would hash passwords before saving them to the database, add authentication and authorization, and use rate limiting to prevent too many requests. I would also validate user inputs, use environment variables to protect sensitive information, enable HTTPS, and handle errors safely.

### 8. Why did you need to add the `!` (definite assignment operator) to your entity properties?

I used the `!` operator to tell TypeScript that a property will be assigned a value later, even if it is not initialized in the constructor. It helps prevent definite-assignment errors when TypeORM manages the entity properties.

### 9. What are the benefits of explicitly defining column types (e.g., `type: 'varchar'`) in your entities?

Explicitly defining column types makes the database structure clearer and more predictable. It helps ensure that each field uses the correct data type and reduces possible problems when creating or updating database tables.

### 10. How do relationships in TypeORM differ from foreign keys in raw SQL? What are the advantages?

In raw SQL, foreign keys are used to connect records between database tables. In TypeORM, relationships such as `ManyToOne` and `OneToMany` allow developers to define these connections using entity classes and decorators. TypeORM can manage the related database structure and make it easier to access related data through code.