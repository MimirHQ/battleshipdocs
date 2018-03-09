# Battleship Playbook

The playbook is a collection of code snippets that show common programming patterns in Battleship. You will use these plays often, so they will soon become like second nature to you.

You may will encounter many similar programming tasks in your coursework. Build your own playbook to keep track of your programming tricks!

To view the full list of methods available in Battleship, [read the API docs.](api.md)

## Table of Contents

* Basic Plays
	* [Checking if a ship is on your team](#checking-if-a-ship-is-on-your-team)
	* [Checking if a ship is in range](#checking-if-a-ship-is-in-range)
	* [Moving towards a fixed coordinate](#moving-towards-a-fixed-coordinate)
	* [Changing behavior on different turns](#changing-behavior-on-different-turns)
* Advanced Plays
	* [Firing until a ship sinks](#firing-until-a-ship-sinks)
	* [Looping over every ship in a list](#looping-over-every-ship-in-a-list)
	* [Find the minimum or maximum ship in a list](#find-the-minimum-or-maximum-ship-in-a-list)
	* [Sorting a list of ships](#sorting-a-list-of-ships)
	* [Tracking information over multiple turns](#tracking-information-over-multiple-turns)
* Elite Plays
	* [Grouping blocks of code into functions](#grouping-blocks-of-code-into-functions)
	* [Using seeded randomness](#using-seeded-randomness)
	* [Casting a ship to a subclass](#casting-a-ship-to-a-subclass)
	* [Sharing information between ships of the same class](#sharing-information-between-ships-of-the-same-class)

## Basic Plays

### Checking if a ship is on your team

```java
if (this.isSameTeamAs(ship)) {
	// Don't shoot, they're friendly!
}
```

### Checking if a ship is in range

```java
Ship target; // Target ship chosen somehow...
if (arena.isInRange(this, target)) {
	// I've got you in my sights!
}
```

### Moving towards a fixed coordinate

```java
@Override
protected void doTurn(Arena arena) {
	int goalX = 7;
	int goalY = 2;
	// Moving towards (7, 2) from any point on the map
	// Note: this only works if there are no obstacles in the way
	Coord coord = this.getCoord();
	if (coord.getY() > goalY) {
		this.move(Direction.NORTH);
	} else if (coord.getY() < goalY) {
		this.move(Direction.SOUTH);
	}
	if (coord.getX() > goalX) {
		this.move(Direction.WEST);
	} else if (coord.getX() < goalX) {
		this.move(Direction.EAST);
	}
}
```

### Changing behavior on different turns

```java
@Override
protected void doTurn(Arena arena) {
	// Don't forget that the first turn is numbered 0!
	if (arena.getTurn() % 2 == 0) {
		// Do something on even-numbered turns
	}
	if (arena.getTurn() > 15) {
		// After 15 turns of waiting, I will unleash...
	}
}
```

## Advanced Plays

### Firing until a ship sinks

### Looping over every ship in a list

### Find the minimum or maximum ship in a list

### Sorting a list of ships

### Tracking information over multiple turns

## Elite Plays

### Grouping blocks of code into functions

### Using seeded randomness

### Casting a ship to a subclass

### Sharing information between ships of the same class
