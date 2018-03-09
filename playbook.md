# Battleship Playbook

The playbook is a collection of code snippets that show common programming patterns in Battleship. You will use these plays often, so they will soon become like second nature to you.

You may will encounter many similar programming tasks in your coursework. Build your own playbook to keep track of your programming tricks!

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

### Changing behavior on different turns

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
