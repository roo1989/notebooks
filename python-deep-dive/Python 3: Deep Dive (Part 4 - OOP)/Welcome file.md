# Objects and Classes

## What is an Object.
An object you can think of as a container that has two main parts.

### Data -> State -> Attribute (default)
<hr />
Data are the things that describe the well attributes of any thing.
Let's take a car attribute for example.

 - Brand -> Opel
 - Sub brand -> Astra
 - Color -> Black
 - Transmission -> Manual
 
 Those are all attributes or state of the car.
 In Python, how you would access those attributes are normally with a dot notation.
 Example:

    car.brand -> "Opel"
    car.sub_brand -> "Astra"
    car.color -> "Black" or "#0000"
    car.transmission -> "Manual"

###  Functionality -> Behavior -> Methods (default)
<hr />
Functionality or Methods can be described as things that the car can do. These are normally in Python methods.<br>
Let's take a car methods for example.

 - Accelerate -> 20km
 - Steer -> -15, left
 - Break -> Pressure

Again these methods would be accessable through the dot notation but as methods(functions) instead of attributes (variables).
Example:

    car.accelerate(20)
    car.steer(-15)
    car.break(5mt)

## Creating an Object.

In many languages (C++, Java, Python) we use Classes or Types to create these objects. Think of a class as a blueprint for an object.

To create an object from a class also known as a type, we create instances of that class with different attributes and methods.

Classes themselfs are an object just like everything else in Python. And when we reference class to a type as well. Python Tuples and Lists are also classes but we refer to them as types.
Classes are callabel, `MyClass()` can be called in Python just like that.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg2Mjc1MTkzOCwtODg1OTU5MzE2XX0=
-->