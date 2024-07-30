# Design Principle

https://java-design-patterns.com/principles/
```
KISS
YAGNI
Do The Simplest Thing That Could Possibly Work
Separation of Concerns
Keep things DRY
Code For The Maintainer
Avoid Premature Optimization
Minimise Coupling
Law of Demeter
Composition Over Inheritance
Orthogonality
Robustness Principle
Inversion of Control
Maximise Cohesion
Hide Implementation Details
Curly's Law
Encapsulate What Changes
Boy-Scout Rule
Command Query Separation
Murphy's Law
Brooks's Law
Linus's Law
```

# SOLID PRINCIPLES

## SINGLE RESPONSIBILITY PRINCIPLE
every class should have only one responsibility
```Animal.class should not contain Car functions()```

## OPEN CLOSED PRINCIPLE
software entities (classes, modules, functions) should be open for extension, but closed for modification - design by contract
```AreaCalculator.class should not calculate area of Shapes (Circle.class, Square.class) instead each class should calculate inside thier class```

## LISKOV SUBSTITUTION PRINCIPLE
objects of a superclass shall be replaceable with objects of its subclasses without breaking the application
```mother&child • bird!=dog, bird=eagle```

## INTERFACE SEGREGATION PRINCIPLE
Clients should not be forced to depend upon interfaces that they do not use... no generalpurpose interface
```fly() method in Bird.interface should be move to FlyingBird.interface```

## DEPENDENCY INVERSION PRINCIPLE 
Depend upon abstractions, [not] concretes
```Engine.Class should not be initialized inside Car.Class but instead it should be constructor injected```

### [Dependency Injection](/App/Android/Architecture/Pattern/Dependency)
DIP sets the guideline for creating loosely coupled systems using abstractions, while DI provides the means to implement this principle by injecting dependencies




