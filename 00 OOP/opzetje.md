# Object Oriented Programming

In this module, you'll implement several exercises with use of a programming paradigm called Object Oriented Programming (OOP). OOP is a way of structuring your code by bundling properties and behaviours into individual objects. It enables you to quickly write effective and abstract code that is easy to use, without having to remember every single detail of how it was implemented.

TODO HIER MOET NOG EEN VIDEO OID. ![embed](https://player.vimeo.com/video/372428821) <- deze hebben we al, en is inhoudelijk al best wel compleet. Op zich zouden Queue en GoC ook als introductie kunnen dienen voor de basisprincipes.

## Familiarisation and practice

Before we get ourselves into implementing more complicated OOP principles, let's first familiarise ourselves with the simpler ones!

1. If you haven't yet, create an account at [GitHub](https://github.com/join). For now, you'll only need it to access the Game of Cards exercises.
2. Practice with [Queue](https://lab.cs50.io/minprog/programmeren-2/2019/problems/queue/lab)
3. Practice with [Game of Cards](https://lab.cs50.io/minprog/programmeren-2/2019/problems/cards/lab)

## Basic Inheritance

A set of classes will be used by the car manufacturer Tesla to keep track different types of cars. All cars have their own unique Vehicle Identification Number (VIN), a price, and battery capacity. There are three types of vehicles:

| Car model | Description                                       | Example `__str__()` output  |
|-----------|---------------------------------------------------|-----------------------------|
| Model 3   | The cheapest car currently in offering, at $38000 | VIN: 123, $38000, 40kwh     |
| Model S   | A more luxurious model, priced at $720000         | VIN: 10, $72000, 70kwh      |
| Model X   | SUV model, priced at $80000                       | VIN: 3, $80000, 90kwh (SUV) |

1. Design a class hyrarchy that implements the cars above, and adds a parent class named `Car`.
2. Implement the `Car` class. This class should store the VIN, as every car is obliged to have it stamped on its frame. The first `Car` to be initialized should be numbered 0, the second car 1, etc. Also create
3. Implement the `ModelThree` class.
4. Implement the `ModelS` class.
5. Implement the `ModelX` class.  
6. For the Model S, there is also a Performance version. Implement a class `PerformanceModelS`. The Performance version of the Model S has 30kwh more capacity but is also 30% more expensive than the normal Model S. Make sure you actually use the pricing from the `ModelS` class to calculate the price of the `PerformanceModelS`. This way, if the pricing for the Model S ever changes, the price of the Performance version changes as well.
7. Provide a test program that creates a list of `Car` objects, with at least a couple of all types of cars, and then calls a function that calculates the total price of all three kids of tickets and then a function that prints the number of cars for each type. For this last function, group the Performance and normal versions of the Model S.

## Inheritance and interfaces

In this part of the assignment, you will write a set of classes, and place them in an organized structure. You will first need to make all of the design decisions; you decide whether a class should purely be something to inherit from, something to hold data, or some interface to interact with or manipulate data.

Design four classes that represent modes of transport: `Bike`, `Bus`, `Train`, `Car`. Each of the classes should give initialization methods that enable setting the average speed and cost per kilometre. You should also implement an appropriate `__str__()` method for each of the classes, and provide functions that calculate the `travel_time()` and `travel_cost()` given a distance. Attempts to set an inappropriate value (like `-10` or `very fast!` for average speed, or distance) should stop the program, while providing the user with information on what went wrong. You are free to add a parent class (or multiple) and extend on the modes of transport.

After designing these methods, implement them, create a list of different modes of transport and do the following:

1. Write a function that takes a list with several modes of transport and finds the cheapest mode of transport.
2. Write a function that takes a list with several modes of transport and finds the fastest `Bike`.
3. Write a function that takes a list with several modes of transport and a distance, calculates the total cost.
4. Write a function that takes a list with several modes of transport and a distance, calculates the average time per mode of transport.
5. Public transport methods often get cheaper the more you use them. Write a function that takes a list with several modes of transport, and calculates the average cost for each of the modes of transport, given that `Bus` and `Train` get 20% cheaper if you use them more than 3 times.
