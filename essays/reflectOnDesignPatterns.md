---
layout: essay
type: essay
image: ../img/designPatterns/prototypePatternImage.jpeg
title: "The Patterns of Prototypes"
date: 2024-04-25-24
published: true
labels:
  - Javascript
  - Design Patterns
---

<img width="250px" src="../img/designPatterns/prototypePatternImage.jpeg>

When it comes to thinking of software engineering, you may think, "Oh, engineering a software to run by coding a bunch of things." However, the part that people may not think of is what engineering is the software engineer actually doing.

Design patterns are one of many useful tools and techniques software engineers use to improve the quality, maintainability, and scalability of software systems. It allows for the engineers to reuse proven solutions to common design problems. It, in a way, allows for software engineers to do less work by being influenced by previous works and examples. This can lead to a more efficient coding system, while allowing for the code to be more universally understood.

## Practice

Some of the uses of design patterns include reusability, maintainability, common vocabulary, performance optimization, and recognizable solutions. 

<strong>Reusability -</strong> Design patterns allow for the collection of solutions to recurring problems and can provide a template or blueprint for how to solve the problems. This reusable aspect allows for the developer(s) to build off of pre-existing solutions rather than coming up with new ones. 

<strong>Maintainability -</strong>Design patterns promote an organized approach to software design. They help by creating code that is easier to understand which leads to easier future modifications and maintenances.

<strong>Common Vocabulary -</strong> Since design patterns establish common vocabulary for developers, it allows for easier discussion, communication, and even collaboration.

<strong>Performance Optimization -</strong> Certain design patterns can also optimize performance by structuring the code in a more efficient way. By doing this, it allows for the ideal optimization time in terms of solutions for certain problems.

<strong>Recognizable Solutions -</strong> Since design patterns were created by the software engineering community, it allows for the solutions to the problems to be fairly recognizable, allowing for a more efficient understanding of what the code is doing in itself, but also within the system.

## Popular

Design patterns have three broad categories with different types of design patterns within them. The three categories include Creational Design Patterns, Structural Design Patterns, and Behavioral Design Patterns.

Some popular design patterns in the creational category include the Factory Method, Singleton, and Builder.

Briefly:
The <strong>Factory Method</strong> defines an interface for creating objects, but allows subclasses to alter the type of objects that will be created.
The <strong>Singleton</strong> method ensures a class has only one instance and provides a global point of access to it.
The <strong>Builder</strong> method separates the construction of a complex object from its representation, allowing the same construction process to create different representations.

Some popular design patterns in the structural category include Adapter, Decorator, and Facade.

Briefly:
The <strong>Adapter</strong> method allows for incompatible interfaces to work together by providing a wrapper with a compatible interface.
The <strong>Decorator</strong> method adds behavior or responsibilities to objects dynamically without altering their structure.
The <strong>Facade</strong> method provide a simplified interface to a set of interfaces in a subsystem, making it easier to use.

Some popular design patterns in the behavioral category include Observer, Strategy, and Command.

Briefly:
The <strong>Observer</strong> method defines a one-to-many dependency between objects where if one object changes state, all its dependents are notified and updated automatically.
The <strong>Strategy</strong> method defines a family of algorithms, encapsulates each one, and makes them interchangeable and allows the algorithm to be selected at runtime.
The <strong>Command</strong> method encapsulates a request as an object, thereby allowing parameterization of clients with different requests, queuing, logging, and undoable operations.

## Personal Examples

Below is an example of singleton design pattern.

```angular2html
class StuffsCollection {
  constructor() {
    // The name of this collection.
    this.name = 'StuffsCollection';
    // Define the Mongo collection.
    this.collection = new Mongo.Collection(this.name);
    // Define the structure of each document in the collection.
    this.schema = new SimpleSchema({
      name: String,
      quantity: Number,
      owner: String,
      condition: {
        type: String,
        allowedValues: ['excellent', 'good', 'fair', 'poor'],
        defaultValue: 'good',
      },
    });
    // Attach the schema to the collection, so all attempts to insert a document are checked against schema.
    this.collection.attachSchema(this.schema);
    // Define names for publications and subscriptions
    this.userPublicationName = `${this.name}.publication.user`;
    this.adminPublicationName = `${this.name}.publication.admin`;
  }
}

/**
 * The singleton instance of the StuffsCollection.
 * @type {StuffsCollection}
 */
export const Stuffs = new StuffsCollection();
```

In this case, the singleton instance is named 'Stuffs' and it is created as an export of 'new StuffsCollection()'.

The singleton characteristics are the private constructor 'StuffsCollection', the static instance of 'Stuffs', and the global access 'Stuffs'. The constructor is not directly accessible outside the class, the instance is exported as a constant and represents the single instance of 'StuffsCollection', and the global access instance can be imported and used globally across modules within the application.

The good parts of the prototype design pattern is the reduced subclassing, like allowing existing objects to be copied leading to the reduced need for subclassing. Prototype design patterns also allow for the flexibility in object creation, improved performance, simplified object creation, and dynamic object creation. However, on the flip-side, prototype design patterns may require what they call 'deep copying' which is to ensure that the entire object graph is cloned correctly. It may also be necessary to manage cloned objects which also adds complexity. So, like everything else in the algorithm, computer science, software engineering world, certain solutions and techniques are useful for certain scenarios and they all have their fair share of pros and cons depending on what is being desired from the solution.

## Conclude

Overall, if there was anything to be taken-away from this paper, it should be the purpose of design patterns and how big of a role it can play in the software engineering world. It may seem minor, unique, and maybe even irrelevant to beginners, but in the long run, it is extremely useful and time-efficient. Coding and creating software takes enough time, might as well use our reliable resources from our community to not only save us time, but save the future developers time when modifying or updating our code.
