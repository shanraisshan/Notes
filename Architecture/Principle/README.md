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

## SINGLE RESPONSIBILITY PRINCIPLE [->](https://youtu.be/x1fqWjG8RVE?t=162)
every class should have only one responsibility
```Circle.class should not contain print function()```

## OPEN CLOSED PRINCIPLE [->](https://youtu.be/x1fqWjG8RVE?t=298)
software entities (classes, modules, functions) should be open for extension, but closed for modification - design by contract
```Circle.class & Rectangle.class should implement IShape.interface which will contain area() function```

## LISKOV SUBSTITUTION PRINCIPLE [->](https://youtu.be/x1fqWjG8RVE?t=471)
child class must be substitutable for thier parent class
```mother&child • bird!=dog, bird=eagle```

## INTERFACE SEGREGATION PRINCIPLE [->](https://youtu.be/x1fqWjG8RVE?t=607)
Classes should not be forced to implement a function they they do not need... no general purpose interface
```fly() method in Bird.interface should be move to FlyingBird.interface • Break IShape into I2DShape I3DShape```

## DEPENDENCY INVERSION PRINCIPLE [->](https://youtu.be/x1fqWjG8RVE?t=799)
Depend upon abstractions, [not] concretes... high level classes should not depend on low level classes, both should depend on abstraction
```Engine.Class should not be initialized inside Car.Class but instead it should be constructor injected```

### Dependency Injection [->](/App/Android/Architecture/Pattern/Dependency)
DIP sets the guideline for creating loosely coupled systems using abstractions, while DI provides the means to implement this principle by injecting dependencies




