## Table of Contents

[[_TOC_]]

## 1. Main Page

| Task/Part | Contributors | Description/Notes |
|-----------|--------------|-------------------|
| Main Page | Abdul | Design Documentation Wiki Page/Main Page. |
| Intro | Shahob | Introduction to Design Documentation |
| Class Diagrams | Shahob, Abdul, Willie | Class Diagram and description of classes |
| Interface Mockup | Octavio | Wireframes for the screens of the game |
| File Formats | Shahob | File formats that will be used and how they will be used in the game |
| Dev Environment | Logan | Describes the IDE, tools, and external libraries that will be used for the project |
| Patterns | Willie | Descriptions of patterns and how they will be used |
| Summary | Logan | Summary of document + table of terms |

## 2. Introduction

### Overview

The purpose of this game is to teach children (ages 7-13 years old) how to be responsible by making them take care of a virtual pet. In order to do this, the pet has vital statistics that are constantly depleting such as fullness, happiness, and sleep. These force the player to be a responsible pet owner since they have an effect on another statistic, the pet’s health. The player also has to handle random events that affect their pet by making proper decisions that don’t hinder their pet’s health. This forces the player to also develop their judgment skills. The game requires several different features such as multiple screens, loading and saving games and vital statistics tracking. These requirements are further outlined in the Project Requirements section in the references below.

### Objectives

The goals of this document are to describe how the project is going to be implemented, describe what the application is going to look like, and provide more details on how the project is going to work. These goals will be achieved through class diagrams, wireframes, and descriptions of file formats, development environments, and software patterns. There will also be explanations as to why we made certain decisions. The objective of the game is to maintain the pet’s life for as long as possible and to teach the user how to properly care for their pet. It is meant to be a fun and entertaining experience as much as an educational tool for pet owners.

### References

* [Requirements Documentation](Project-Documentation)
* [Project Specification](https://westernu.brightspace.com/d2l/le/enhancedSequenceViewer/67850?url=https%3A%2F%2F832d4e9b-197e-4ab6-a2ca-c4f7aae74b20.sequences.api.brightspace.com%2F67850%2Factivity%2F2642641%3FfilterOnDatesAndDepth%3D1)

## 3. Class Diagrams

![class diagram.jpg](uploads/6a030c1ffad0b4766d5b6bfe81ae086c/class_diagram.jpg)

**UI Interface:** this abstract class will represent a screen for the game. it includes the size of the screen, displays the elements of a screen, and reads user input.

**MainMenu:** this class will represent the main menu screen of the game. it will display the elements of the main menu screen as well as load previous save slots of the user and will implement all the methods and attributes of the abstract UI class.

**NewGame:** this class will represent the screen to create a new save slot; it will load the elements when the user is creating a new save slot and implement all the methods and attributes of the abstract UI class.

**Instructions:** this class will represent the pop-up screen used to display instructions to the user. It will display instructions and implement all the methods and attributes of the abstract UI class.

**Events:** this class will represent the pop-up events (Bitlife) that affect the pet. It will have a timer attribute to keep track of when to display an event and it will determine the reward or debuff of the option the user selects. It will also implement all the methods and attributes of the abstract UI class

**ParentalSettings:** this class represents the the parental log in and parental settings screen. It will have a password attribute for the parent to log in and will include the actions exclusive to the parent (setting a play time limit, seeing and resetting player stats and reviving dead pets.) It will also implement all the methods and attributes of the abstract UI class

**Gameplay:** This class represents the main logic of the game. It tracks the time played, decreases the stats of the pet, processes the user's commands and saves and exits the game. It will also implement all methods and attributes of the abstract UI class.

**Pet:** This class will represent the user's pet. It has all the attributes relating to the pet (health, fullness, sleepiness, happiness, state, sprite, etc) and methods to change the attributes of the pet (setters and getters).

**Action:** This class will represent all the actions the user can do with the pet. It will have a cooldown timer for each action (feeding pthe et, giving the pet a gift, taking the pet to the vet, etc.)

**GameInventory:** This class represent the inventory of the user for one save file. It will display the inventory and have methods to use items and add items and will save the inventory upon the user's exit.

## 4. User Interface Mockup: https://balsamiq.cloud/snbuiqy/pt1xrvq

Our user interface was created on a set of design principles:

* Clarity & simplicity
  * Intuitive, self-explanatory buttons that minimize visual complexity
* Consistency
  * Repeated design features and button placement and designs (status bars and dropdown menus used in several screens)
  * Repeated fonts and box styles
* visual hierarchy
  * The most important buttons are placed in the middle of the screen, and screen navigation buttons are always placed in the top right of the screen.
* User-Centric design
  * UI is designed to be appealing to our users visually (5-13-year-old children)
  * Uses bright colors and fun visuals to keep users interested
    * Uses old-school bit art designs to be visually appealing

### Main Menu

![image](https://github.com/user-attachments/assets/c8f1cc9e-364a-420c-914d-1c1ea574c348)

* Allows user to access new game creation, load previous game (selected by drop down menu), exit game, access to parental controls screen, access to instructions screen.

### New Game/Pet Selection

![image](https://github.com/user-attachments/assets/71f09c9b-ac66-46e1-9c94-ed0cbeb4e15b)

* Displays details and stats about each animal, allows the user to write their pet name, select animal type and save new game data. This button will return the user to the main page.

### 

### Game Play

![image](https://github.com/user-attachments/assets/26ef4ce7-356f-45be-a477-868d4c67a14a)

* The screen contains a row of buttons in the lower part of the screen that allow sure to do core actions. Two dropdown list inventories contain food and gifts. After selecting a food/gift, the user can give it to their pet by using the feed/gift button. Major stats are displayed in the upper left of the screen. The exit and save game button is located in the upper right side of the screen.

### Event Notifications

![image](https://github.com/user-attachments/assets/e9244117-9c82-47e3-8f0c-a82d7fa51291)

![image](https://github.com/user-attachments/assets/e9eaac48-d96c-416c-801b-c148e1f32029)

![image](https://github.com/user-attachments/assets/7db23244-73e0-4e6b-9de3-fe38d915d8ff)

* The event notification screen (our team’s bonus feature) allows the user to read the event and choose an action to do for the event in the dropdown menu options. This screen pops up randomly every 30 seconds to 1 1min30sec in the game. Once the user selects an action and does it, the result will be displayed. If the answer is correct, the user will be awarded a gift. If not, the user will have some percentage deducted from one of the status bars (health, fullness, sleep, happiness).

### Instructions

![image](https://github.com/user-attachments/assets/96464fa4-465d-425b-af68-3f71d8729300)

* The instructions will be shown in a pop-up window from the main menu. It will have a scroll bar and a bunch of text and images explaining how the game is played.

### Parental Controls

<span dir="">![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfPOLNlsBKQyjNE8Bq2U5gve-5VR-8w0M03qyHL1O1oQ3UaY_U7Z3dWRVZUpFTFxMm0dfFDV01uMI5INGtVdU34CUS3DMDEeVhkLVWnmxNuFrn_Vk_ikMfrMARP4F4R58XzYlyf?key=P1zVv2Mzw0rMCu3wENgDSlPH)</span>

<span dir="">![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdvgHwNYe-vpEGIuMo3ouKIqtFtXhdBx2YBCNlar5GDT_U5eZz20zKv6Qc1aXAAcsmp_z-TVoj6gHa3GNSxYOr1cqfRoFCCnIPgPZfWJ6ss6L4IblPOW8p-XrxoKsLnnklebKG0yA?key=P1zVv2Mzw0rMCu3wENgDSlPH)</span>

* The password screen is accessed from the main menu screen. Once the correct hardcoded password is entered, a parent can see play stats, reset play stats, set play time limits, input time limits, and select pets to revive. The user can return to the main menu from both screens by pressing the return button in the top right.

## 5. File Formats

To store both data on the virtual pets and player for each save slot, we will be using CSV files. The reason for this is that they are convenient to parse through, and there is not a lot of data for us to store. There will be one CSV file that contains data on all three save slots:

![image](https://github.com/user-attachments/assets/b533a43c-99c4-4c96-b15c-005826e69d4c)

**Health**, **happiness**, **sleep**, and **fullness** are all ratios out of 100 that represent the pet’s vital statistics. **state** represents the current status of the sprite as a result of their statistics. **sprite** is the type of pet, e.g. goomba, cat, dog, and dragon. **play_time** is the number of minutes the save slot has been played for (convenient for the parent if separate save slots are used for separate players). **num_session** represents the total number of play sessions for that save slot. **score** represents the player(s)’s score for that save slot. **name** represents the name of the virtual pet. The average play time per session can be derived from play_time and num_session, so there is no need to store it in the CSV file.

In order to use the random events, they will be stored in a JSON file. The reason for this is that there are a lot of events and they can be classified into different types based on the type of pet they apply to (general, cat, dog, goomba, dragon). A JSON file easily allows the program to get the events from one of these categories in order to select one for the user. The JSON file will look something like this:

![image](https://github.com/user-attachments/assets/d12c0de1-2abd-41e5-8ac4-060d60d3c059)

A [random number generator](https://www.w3schools.com/java/java_howto_random_number.asp) will be used to select each event. We will be using the Jackson library in order to use JSON in Java.

To keep track of the inventories in each of the save slots, we will be using a JSON file. This is because it allows us to easily access the specific amounts for each item for the save slot in use. It is also more organized than a CSV file. The JSON file will look something like this:

![image](https://github.com/user-attachments/assets/b685a1f0-d135-459b-ac82-9fc62c799fdc)

We will be using the Jackson library in order to use JSON in Java.

To store data for the parent, we will be using a CSV file. Again, the reason for this is that they are convenient to parse through, and there is not a lot of data for us to store. The CSV file will contain one line of data:

![image](https://github.com/user-attachments/assets/c9242767-d360-4111-931e-7d27d073f13d)

**pass** is the password of the parent, and it is used to verify what the password the parent enters on the parental controls screen. **limit_start** represents the starting time of the play time limit for all players. In this example, it is 7 PM. **limit_end** represents the ending time of the play time limit for all players. In this example, it is 8 AM.

## **6. Development Environment**

For the development of the Java program, the team will use the following environment:

IDE:

* VSCode will be used as the primary IDE. VSCode provides excellent Java support through extensions like Java Extension Pack, which includes features such as syntax highlighting, IntelliSense, and debugging.

External Libraries:

* JavaFX will be used for creating the GUI. This library is built for modern desktop applications with rich user interfaces and is compatible with Windows systems.
* Jackson Library will be used to work with JSON files.
* Optionally, additional libraries may be used depending on the project’s requirements, such as Apache Commons for utilities or Google Guava for advanced collections and utilities (if necessary).

Tools:

* JUnit 5 will be used for unit testing.
* Javadoc will be used for generating documentation. Every class, method, and important logic will be documented with clear descriptions to ensure clarity and allow modifications to be easier to implement

This setup will ensure efficient development of the Java program that runs on Windows, is well-tested using JUnit, and has clear documentation through Javadoc.

## **7. Patterns**

### Game Loop Pattern

* **Description:** A game loop runs continuously during gameplay. For each iteration of the loop, it processes user input, updates the game state, and renders the game. It also tracks the passage of time to control the rate of gameplay.
* **Why it is appropriate for the project:** it is appropriate for the project since a gameplay loop controls the key features of a game. 
* **How it will be used:** It will be used to slowly decrease the pet’s sleepiness and fullness as time passes. It will keep track of the user’s playing time for parents to view and will compare the playing time to a limit set by the parent (if applicable). It will load the game screens and pet sprites. It will keep track of and update the user’s score. It will process the mouse inputs and keyboard inputs from the user. 
* **Reference:** https://gameprogrammingpatterns.com/game-loop.html 

### Type Object Pattern

* **Description:** There will be a type object class and a typed object class. Each type of object instance represents a different logical type. Each typed object stores a reference to the type object that describes its type. Instance-specific data is stored in the typed object instance, and data or behavior that should be shared across all instances of the same conceptual type is stored in the type object. Objects referencing the same type of object will function as if they were the same type. It is similar to subclasses but doesn’t have the physical hard-coded subclasses.
* **Why it is appropriate for the project:** It is appropriate for the project since we are required to have multiple different screens. 
* **How it will be used:** We will make a type class for UI screens. Typed classes will be made for the specific screens (main menu screen, new game screen, gameplay screen, instructions screen, and parental settings screen.)
* **Reference:** https://gameprogrammingpatterns.com/type-object.html 

### Keyboard Shortcuts Pattern

* **Description:** a way for users to do repetitive tasks faster using their keyboard.
* **Why it is appropriate for the project:** It is appropriate for the project since we are required to include keyboard shortcuts.
* **How it will be used:** we will create shortcuts for playing with the pet (P), viewing the user’s inventory (E), taking the pet to the vet (V), gifting a gift to the pet (G), putting the pet to sleep (S), feeding the pet (F) and returning back to main menu (ESC).
* **Reference:** https://ui-patterns.com/patterns/keyboard-shortcuts 

### Singleton Pattern

* **Description:** A class has only one instance and can be accessed globally.
* **Why is it appropriate for the project:** we would only have 1 pet, 1 inventory and, 1 parent instance at a time. 
* **How it will be used:** There will be only 1 instance of a pet, 1 inventory instance and, 1 parent instance while the game is running. 
* **Reference:** https://gameprogrammingpatterns.com/singleton.html

### Observer Pattern

* **Description:** Define a one-to-many dependency between objects so when one object changes state, all its dependents are notified and updated automatically.
* **Why it is appropriate for the project:** It is appropriate for the project since the user needs to receive feedback from the game when actions are taken.
* **How it will be used:** GUI components will be connected to pet statics. When the statics reach low levels, the sprite will change. When BitLife options are selected, GUI elements may be updated to reflect the choice (to do increase/decrease in statics). 
* **Reference:** https://gameprogrammingpatterns.com/observer.html

### Modelled View Controller Pattern

* **Description:** breaks an application into three parts: the Model (handles data), the View (what users see), and the Controller (connects the two).
* **Why it is appropriate for the project:** it is appropriate for the project because there is a UI component and a back-end component to this project. MVC is a good architecture to use when dealing with both front-end and back-end components.
* **How it will be used:** The UI classes and logic classes will be connected through a Gameplay class. 
* **Reference:** https://www.geeksforgeeks.org/mvc-design-pattern/

### Vertical Dropdown Pattern

* **Description:** The user puts the mouse cursor over one of a list of items, a drop-down list of new options is shown below the list item the mouse cursor is pointing at is shown.
* **Why it is appropriate for the project:** it is suitable for the project because it will not take up a lot of space on the screen and is a very effective way to display lists of 2 - 9 items (it fits with the number of different gifts and food items we have). 
* **How it will be used:** The user’s inventory will be represented with 2 dropdown menus. One is for the users of gifts to give to the pet and the other for the user’s food items to feed the pet. 
* **Reference:** https://ui-patterns.com/patterns/VerticalDropdownMenu

### Dashboard Pattern

* **Description:** A high-level overview of data that allows for discovering actionable trends. It also provides real-time insight into the current state of the most important metrics of a system.
* **Why it is appropriate for the project:** it is appropriate for the project because keeping track of the pet’s stats/status is a huge component of the game. 
* **How it will be used:** Status bars will show the stats (health, fullness, sleepiness, happiness) in a visual way to the user. 
* **Reference:** https://ui-patterns.com/patterns/dashboard

### State Pattern

* **Description:** allowing an object to alter its behavior when its internal state changes.
* **Why it is appropriate for the project:** it is appropriate for the project because when the pet is in certain states, some commands may be not accessible to the user (all commands when in normal state, no commands in dead state, etc).
* **How it will be used:** It will be used to set the state of the pet as well as prevent users from using certain actions/commands depending on the pet’s state.
* **Reference:** https://gameprogrammingpatterns.com/state.html

### Command Pattern

* **Description**: a method call wrapped in an object, letting users call different requests, queue or log requests, and support undoable operations.
* **Why it is appropriate for the project:** it is appropriate for the project because it can be used to process input and translate it into a meaningful action in the game(feeding pet, exercising pet, going back to the main menu, etc)
* **How it will be used:** The _feed_ and _give gift_ commands will allow the user to decide what item (gift or food) to use for their pet. It will also be used to process user input throughout the game. 
* **Reference:** https://gameprogrammingpatterns.com/command.html

## **8. Summary**

This design documentation outlines the key decisions and components for the development of our Java-based software application. The project focuses on delivering a solution to manage virtual pets, allowing users to interact with, track, and care for their pets through a user-friendly interface.

The core design of the software emphasizes a Model-View-Controller architecture to separate the business logic from the user interface, ensuring maintainability and flexibility. The JavaFX library is used to build the graphical interface, providing an intuitive layout for users. The core business logic includes classes like UI, Pet, and Actions, designed to handle various operations such as adding pets, tracking pet attributes, and managing user interactions.

Data will be stored in JSON format, with a clear structure that stores essential pet attributes, making it easy to retrieve and update pet information. We will utilize JUnit for rigorous unit testing and Javadoc to document the code, ensuring clarity and future maintainability.

By adhering to design patterns like Singleton to contain all the metrics for a single animal and Command for interacting with the pet, the system is lightweight and robust. The user interface has been wireframed, focusing on a clean layout that promotes ease of use, and all data interactions are planned to be straightforward, allowing users to quickly access and modify pet data.

Overall, the design aims to meet the project requirements while ensuring a robust, user-friendly, and maintainable solution for virtual pet management

### Table of Terms

| Acronym | Definition |
|---------|------------|
| GUI | Graphical User Interface |
| VSCode | Visual Studio Code |
| IDE | Integrated Design Environment - Where coding will be done |

