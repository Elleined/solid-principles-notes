# solid-principles-notes

# What is SOLID Principles
- It is a software structure design conceptualized by Robert C. Martin also known as Uncle bob that changed the way of writing software. It also ensure that software is modular, easy to understand, debug and refactor.

# SOLID stands for
`S (Single Responsibility Principle/ SRP)`  
`O (Open Closed Principle/ OCP)`  
`L (Liskov Substitution Principle/ LSP)`  
`I (Interface Segregation Principle/ ISP)`  
`D (Dependency Inversion/ DI)`  

# Why do need SOLID Principles
- To avoid bad design
- To reduce code complexity
- To remove tight coupling of classes
- Separate each class responsibility 
- To define class relationship between other classes.

# Single Responsibility
- A class should only have 1 reason to change.
###### For example: When you're refactoring a class and ended up refactoring all over the place that is unrelated to the one you really want to change that is violation of SRP. Because class should only have 1 reason to change if you will refactor a Controller class youre reason to refactor it, is because you need to change how the request will be handled not because you need to change it because it was breaking when you change some code in your codebase.

###### Another example: If you have a method named saveFoo() and that methods also performs the validations for saving Foo its wrong validations must be in separate class doing only validations for Foo so that if you need also to update Foo you can reuse the validations code because it in separated class.

- A class should only have one and only one responsibility, task, or job nothing else. 
###### For example: In microservice architecture there are Controllers, Services, and Repositories each has own responsibility. Controllers for handling the request, Services for handling the Business logics, and Repositories for talking to database. Same concept for all the other classes when write a class named FooController that class should do handle the request only nothing else.

#### Benefits of Single Responsibility
- Maintanable code
- Easy to refactor
- Reusable code


