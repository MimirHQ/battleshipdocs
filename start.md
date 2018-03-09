# Getting Started

## Install the Battleship Core Library

If this is your first time playing, install the battleship core library.

Install the battleship library at the same directory level as all the other battleship missions. Run these commands in your terminal to go to the correct directory level and clone the library from GitHub.

```
cd ..
git clone https://github.com/MimirHQ/battleship.git
```

## Preparing for the Mission

The code for this mission lives in its own folder, called a package. The folder name may vary based on how your instructor named the project. To run the mission, you must change the folder name to match the package name. Find the package name at the top of any Java file in the package: it is the same as the mission ID from the briefing.

If you are inside the folder in your terminal, navigate one level up before you rename. Run the commands below.

```
cd ..
mv currentfoldername missionid
```

Then conduct reconnaissance on the enemy ships by reading their source files.

## Developing Your Ship

Implement your ship in `PlayerShip.java`. [Read the API guide](api.md) to learn how to use the battleship methods.

## Running the Mission

Navigate to the directory level that contains the battleship core library and the mission package. Compile and run the mission by running these commands in your terminal. Use the real mission id instead of `missionfoldername`.

```
javac missionfoldername/Main.java
java missionfoldername.Main
```

Read the mission results in your terminal and study the output files to learn more about how your ship performed.
