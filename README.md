# Undo and Redo Command Project

## Objective 
Use data structures and algorithms to simulate **undo** and **redo** operations for a sequence of user actions and store them in a text file.

## Problem 

You are developing a program to simulate **undo** and **redo** operations for a sequence of user actions. The program uses two data structures (Undo and Redo) to keep track of performed actions so that the user can navigate to new or previous actions.

To interact with the program, the user requires a display menu to choose whether to **print all performed actions**, **add a new action**, **Undo last action**, **Redo last undone action**, or **exit the program**.

> All the performed actions are stored in a text file called [actions.txt](https://github.com/SAFCSP-Team/undo-redo-command-project/blob/main/src/actions.txt).

## Features 
-  Use two data structures:
    - **Undo**: for performed actions.
    - **Redo**: for undone actions.
- Display a menu for user interaction.
- Read the performed actions from `actions.txt` into the **Undo** data structure at startup.
- Print all the performed actions from the **Undo** data structure.
- Add a new action to the **Undo** data structure(clears the **Redo**).
- Undo the last action (moves it from **Undo to Redo**).
- Redo the last undone action (moves it from **Redo** back to **Undo**).
- Provide clear feedback for invalid operations (e.g., empty Undo/Redo).
- When the program exits, save the **Undo** data to `actions.txt`.

## Implementation
- Create a menu that takes input from the user. Based on the user's input, do the following:
  - 1: Print all performed actions
  - 2: Add a new action
  - 3: Undo last action
  - 4: Redo last undone action
  - 5: Exit.

- Create a class `UndoRedoManager` with the following methods:  
  - Create a data structure called **Undo**, and save the actions from the `actions.txt` file into it.
  - Create an empty data structure called **Redo**.
  - Create a method called `printAllActions` that prints all the actions from the **Undo** data structure.
  - Create a method called `addAction` that adds an action to the **Undo** data structure.
  - Create a method called `undoAction` that returns and removes the last action from the **Undo** data structure and adds it to the **Redo** data structure, and prints the undone action.
  - Create a method called `redoAction` that moves the last action from the **Redo** back to the **Undo** and prints the redone action.
  - Create a method called `saveActions` that updates the actions in the `actions.txt` with the data from the **Undo** data structure.
  - Create a method called `loadActions` that loads the data to the **Undo** from 'actions.txt' at startup.

## Test case
When the program runs, the user shall see the following menu:
```
Undo/Redo Command Tracker
Enter your choice
-------------------------
1 -> Show all performed actions
2 -> Add a new action
3 -> Undo last action
4 -> Redo last undone action
5 -> Exit

2
Enter action: type Hello
Action added.

2
Enter action: delete o
Action added.

1
Performed actions:
delete o
type Hello

3
Undone: delete o

4
Redone: delete o

5
Goodbye...

```


## Qualification to pass
- [ ] The code should run successfully.
- [ ] Write all the required functions correctly.
- [ ] The program's output shall match the test case output.

