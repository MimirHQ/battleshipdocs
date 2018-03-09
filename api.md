# Battleship API

* [Ship Class](#ship-class)
	* [Setting Base Properties](#setting-base-properties)
	* [Implementing Turn Strategy](#implementing-turn-strategy)
	* [Initialization Methods](#initialization-methods)
	* [Protected Methods](#protected-methods)
	* [Public Methods](#public-methods)
* [Arena Class](#arena-class)
* [Coord Class](#coord-class)
* [Direction Enum](#direction-enum)

## Ship Class

### Setting Base Properties

Modify the base properties of your ship. You have a total of 10 points to distribute amongst the four properties.

* Hull: number of hits it can withstand before being destroyed.
* Firepower: number of shots it can fire on a turn.
* Speed: number of spaces it can move on a turn.
* Range: number of spaces in any direction it can see or fire.

### Implementing Turn Strategy

Program your ship’s strategy by filling in the `doTurn()` method. This method also takes in the game arena as an argument. On each turn, a ship can:

#### Observe

* Can look at other ships within X squares of your ship, where X is the ship’s range value.
* If a ship is in range, you can check its x and y coordinates as well as all of its properties.

#### Move

* Can move up to X spaces, where X is the ship’s speed value.
* Must choose a direction to move in: North, East, South, or West.

#### Fire

* Can fire up to X times, where X is the ship’s firepower value.
* Must give the x and y coordinates of the square to fire at.

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

### Protected Methods

These methods can only be called the ship they belong to.

```java
void move(Arena arena, Direction direction)
void fire(Arena arena, int x, int y)
List<Ship> getNearbyShips(Arena arena)
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

```java
int getXSize()
int getYSize()
int getTurn()
Random getRandom()
```

```java
boolean isInRange(Ship source, Ship target)
Ship getShipAt(int x, int y)
int countLiveShips()
List<Ship> getAllShips()
List<Ship> getAllSpawnedShips()
```

## Coord Class

```java
int getX()
int getY()
```

## Direction Enum

```java
Direction.NORTH
Direction.SOUTH
Direction.WEST
Direction.EAST
```
