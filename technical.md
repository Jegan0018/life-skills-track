# SOLID Principles for Codebase Refactoring

## Introduction

Refactoring the code base is a crucial step in software development projects to increase the code's quality, extensibility, and maintainability. Adhering to the SOLID principles is a tried-and-true method for directing the refactoring process. The term SOLID stands for five core ideas in object-oriented design that support the development of reliable and adaptable programmes.

## Single Responsibility Principle (SRP)

According to the Single Responsibility Principle (SRP), a class should only have one cause for change. In other words, a class need to have just one duty or goal. A class becomes complicated and challenging to manage when it is in charge of too many things. Every class in the codebase is made more focused, modular, and understandable by restructuring it to follow SRP.

## Open-Closed Principle (OCP)

Software entities should be open for expansion but closed for modification, according to the Open-Closed Principle (OCP). New functionality should be provided by extending or overriding existing code rather than altering it. This approach encourages the use of inheritance, interfaces, and abstraction to produce scalable and adaptable programming. We ensure that the codebase is simpler to maintain and extend without adding defects or disrupting existing functionality by using OCP during codebase refactoring.

## Liskov Substitution Principle (LSP)

According to the Liskov Substitution Principle (LSP), objects from a superclass should be interchangeable with those from its subclasses without affecting the program's validity. To put it another way, derived classes ought to be able to take the place of their base classes without resulting in undesirable outcomes. We ensure that the codebase is designed with appropriate polymorphism and inheritance by following LSP during codebase refactoring. This results in more resilient and flexible code.

## Interface Segregation Principle (ISP)

It is recommended under the Interface Segregation Principle (ISP) that clients not be made dependent on interfaces they do not use. Classes should implement smaller, more specialised interfaces rather than big, monolithic ones. Because clients only need to rely on the interfaces containing the methods they need, this notion encourages loose coupling. We improve the codebase's modularity, maintainability, and testability by using ISP during codebase restructuring.

## Dependency Inversion Principle (DIP)

High-level modules shouldn't be dependent on low-level modules, according to the Dependency Inversion Principle (DIP). They ought to both rely on abstractions. Using dependency injection and inversion of control to separate modules and rely on abstractions rather than actual implementations are both encouraged by this approach. We achieve loose coupling, modularity, and simpler testing and maintenance of the codebase by following DIP during codebase remodelling.

## Code Samples
Here are some of the code samples :

### SRP

class OrderCalculator {

    public void calculateTotal() {
        // Calculate total order amount
    }
    
}

class OrderPersistence {

    public void saveToDatabase() {
        // Save order details to the database
    }
    
}

### OCP

interface PaymentProcessor {
    void processPayment(Payment payment);
}
class CreditCardPaymentProcessor implements PaymentProcessor {
    public void processPayment(Payment payment) {
        // Process credit card payment
    }
}
class PayPalPaymentProcessor implements PaymentProcessor {
    public void processPayment(Payment payment) {
        // Process PayPal payment
    }
}

### LSP

abstract class Shape {
    public abstract int calculateArea();
}
class Rectangle extends Shape {
    protected int width;
    protected int height;
    
    public void setWidth(int width) {
        this.width = width;
    }
    
    public void setHeight(int height) {
        this.height = height;
    }
    
    public int calculateArea() {
        return width * height;
    }
}
class Square extends Shape {
    private int sideLength;
    
    public void setSideLength(int sideLength) {
        this.sideLength = sideLength;
    }
    
    public int calculateArea() {
        return sideLength * sideLength;
    }
}

### ISP
interface Printer {
    void print();
}
interface Scanner {
    void scan();
}
interface FaxMachine {
    void fax();
}
class MultiFunctionPrinter implements Printer, Scanner, FaxMachine {
    public void print() {
        // Print document
    }
    public void scan() {
        // Scan document
    }
    public void fax() {
        // Fax document
    }
}

### DIP

class OrderProcessor {
    private OrderRepository orderRepository;
    public OrderProcessor(OrderRepository orderRepository) {
        this.orderRepository = orderRepository;
    }
}

## Conclusion

The SOLID principles offer helpful guidance for codebase remodelling, to sum up. We produce code that is simpler to manage, maintain, and expand by using the Single Responsibility Principle (SRP), Open-Closed Principle (OCP), Liskov Substitution Principle (LSP), Interface Segregation Principle (ISP), and Dependency Inversion Principle (DIP). SOLID-guided codebase restructuring produces software systems that are more durable, adaptable, and scalable. Therefore, in order to enhance the codebase's quality and guarantee its long-term success, it is crucial to take these concepts into account.

## References
https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design
