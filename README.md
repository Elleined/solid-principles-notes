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
- Production ready code.
- Maintanable and Scalable Code.

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


# Open/ Closed Principle
- A class should be open for extension and closed for modification.
###### For Example: You have a class Animal and this class has a subclass named Mammal and now you want to add a subclass to Animal named Reptile you literally should create a Reptile class and extend it to Animal class and everything should be fine. That means that you should model your classes properly in order to achieve this. In this example Animal class is open to extension that Reptile extended to Animal class and closed for modification is that we dont change or minimally changed any code in Animal class just to accomosate the Reptile class

# Liskov Subtitution Principle
- A class should not be force to implement that he can't or able to do.
###### For example: You have Animal interface that has two method eat() and fly() and now you created Bird class that implements Animal interface now thay we can read it that "Bird is a Animal" right?. Now we create Mammal class and implements Animal interface we are now enforce to override the eat() and fly() method But does Mammal can fly? remember we should not force the class to implement the method that he cant do right? The correct approach is that we should create Animal interface has create another interface named FlyingAnimal that extends Animal and have a Bird that implements FlyingAnimal that has fly() method in this approach when we create Mammal class we are not enforce to implement the fly method because fly method is now only in FlyingAnimal interface.

#### Wrong Approach
```
interface Animal {
  void eat();
  void fly()
}

class Bird implements Animal {
  @Override
  public void eat() {}

  @Override
  public void fly() {}
}

class Mammal implements Animal {
  @Override
  public void eat() {}

  @Override
  public void fly() {}
}
```

#### Correct Approach
```
interface Animal {
  void eat();
}

interface FlyingAnimal {
  void fly();
}

class Bird implements FlyingAnimal {
  @Override
  public void eat() {}

  @Override
  public void fly() {}
}

class Mammal implements Animal {
  @Override
  public void eat() {}
}

```

## Behavioral
- Operates in value level
- Preconditions must be same or weaker than supertype. Same concept as contravariance but in value level because it need to be liberal of what you accept.

- Postcondition must be same stronger than supertype. Same concept as covariant but in value level because you must be conservative of what you do.

## Type
- Operates in type level
- Contravariance in parameters
- Covariant in returns
- No new exception and only a subtype of exception in superclass method are allowed in subtypes to be thrown

[Understand Java Variance](https://github.com/Elleined/java-core-notes/blob/main/README.md#variance)
