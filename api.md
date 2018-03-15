# Battleship API

This guide lists all of the methods available to you in Battleship.

* [Ship Class](#ship-class)
	* [Setting Base Properties](#setting-base-properties)
	* [Implementing Turn Strategy](#implementing-turn-strategy)
	* [Initialization Methods](#initialization-methods)
	* [Protected Methods](#protected-methods)
	* [Public Methods](#public-methods)
* [Arena Class](#arena-class)
* [Coord Class](#coord-class)
* [Direction Enum](#direction-enum)

To see common programming tasks in Battleship, [view the playbook.](playbook.md)

## Setting Base Properties

Modify the base properties of your ship. You have a total of 10 points to distribute amongst the four properties.

* Hull: number of hits the ship can withstand before being destroyed.
* Firepower: number of shots the ship can fire on a turn.
* Speed: number of spaces the ship can move on a turn.
* Range: number of spaces the ship can fire, in any direction.

### Initialization Methods

These methods are used to set the properties of your ship.

```java
void initializeName(String name)
void initializeOwner(String owner)
void initializeHull(int hull)
void initializeFirepower(int firepower)
void initializeSpeed(int speed)
void initializeRange(int range)
```

## Implementing Turn Strategy

Program your ship’s strategy by filling in the `doTurn()` method. This method also takes in the game arena as an argument. On each turn, a ship can:

### Observe

* Can search through all other ships in the arena, both enemies and teammates.
* Can check a ship's x and y coordinates as well as all of its properties.

### Move

* Can move up to X spaces, where X is the ship’s speed value.
* Must choose a direction to move in: North, East, South, or West.

### Fire

* Can fire up to X times, where X is the ship’s firepower value.
* Must give the x and y coordinates of the square to fire at.

## Coord Class

Note: Ships do not have a `getX()` or `getY()` method, they have a `getCoord()` method that returns a coordinate object. The coordinate object has the x and y data.

```java
int getX()
int getY()
```

## Direction Enum

In Battleship, y-coordinates increase from low values on the north end of the arena to high values on the south end and x-coordinates increase from low values on the west end to high values on the east end.

```java
Direction.NORTH
Direction.SOUTH
Direction.WEST
Direction.EAST
```

## Ship Class

Some methods can be called on any ship, others can only be called by the ship they belong to.

### Protected Methods

These methods can only be called the ship they belong to.

```java
void move(Direction direction)
void fire(int x, int y)
List<Ship> getNearbyShips()
```

### Public Methods

These methods can be called on any ship.

```java
boolean isSameTeamAs(Ship ship)
String getTeam()
```

```java
Coord getCoord()
int getRemainingMoves()
int getRemainingShots()
```

```java
boolean isSunk()
Ship getSunkBy()
Coord getSunkAt()
```

```java
Ship getName()
Ship getOwner()
int getHealth()
int getHull()
int getFirepower()
int getSpeed()
int getRange()
```

## Arena Class

The arena for the mission or battle is an argument for the `doTurn()` method. It contains other helpful methods that can be used to enhance a ship's strategy.

### Observe Other Ships

```java
boolean isInRange(Ship source, Ship target)
Ship getShipAt(int x, int y)
int countLiveShips()
List<Ship> getAllShips()
List<Ship> getAllSpawnedShips()
```

### Get Mission/Battle Data

```java
int getXSize()
int getYSize()
int getTurn()
```

### Add Pseudorandom Behavior

In Battleship, you should not use truly random behavior, because then we could not easily reproduce the results of a mission or battle! Pseudorandomn behavior follows statistical patterns of randomness, but can be generated in a definite way. To add pseudorandom behavior, call the `arena.getRandom()` method to get the arena's `Random` object. You can learn about the abilities this object gives you in the [Java 8 Random documentation](https://docs.oracle.com/javase/8/docs/api/java/util/Random.html).

```java
Random getRandom()
```
