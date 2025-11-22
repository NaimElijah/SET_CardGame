# **Set Card Game — Multithreaded Java Implementation**

This project is a full implementation of the **Set card game** in Java.
It simulates a real-time game involving both **human players** and **computer players**, a **dealer**, a **visual UI**, and a complete **game engine** that manages:

* Player actions
* Valid set evaluation
* Game flow
* Timers & freezes
* Concurrent interactions
* GUI rendering & input

This is a **multithreaded**, **event-driven**, and **object-oriented** Java system, developed as part of a university assignment focused on concurrency, design patterns, testing, and GUI programming.

---

## 🎮 **About the Game**

Set is a pattern-recognition game where players compete to find “sets” of cards with matching or contrasting features.

Your implementation includes:

* A **dealer thread** that handles the deck, table, reshuffling, hints, and game timing
* Multiple **player threads** (both human-controlled and AI-controlled)
* A **shared table** object managing card placement
* A **configurable environment** loaded from a properties file
* A complete **Swing-based GUI**

---

## 🚀 **Key Features**

### ✔️ **1. Fully Multithreaded Design**

* Each player runs in its own thread
* Dealer is another independent thread
* UI events and keyboard input handled concurrently
* Safe synchronization using locks and atomic operations

### ✔️ **2. GUI Interface (Swing)**

Files related:
`UserInterface.java`, `UserInterfaceSwing.java`, `WindowManager.java`, `UserInterfaceDecorator.java`

Features:

* Real-time GUI updates
* Visual cards & indicators
* Player freezes shown visually
* Keyboard input for human players

### ✔️ **3. Complete Game Engine**

Core components include:

| Component | Description                                                       |
| --------- | ----------------------------------------------------------------- |
| `Dealer`  | Manages deck, table updates, set checks, timing, freezes          |
| `Player`  | Human or computer player, synchronized actions                    |
| `Table`   | Mapping of card slots, validity checks, removal & placement logic |
| `Config`  | Loads all game settings from `config.properties`                  |
| `Env`     | Environment object (UI, config, logger, utilities)                |

### ✔️ **4. Configuration-Driven Gameplay**

Config file: **`config.properties`**
(Cited from the uploaded file → )

Controls:

* Number of players
* UI layout
* Grid size
* Set rules (feature count & feature size)
* Freeze durations
* Dealer reshuffle timing
* Keyboard input mapping
* Logging verbosity

### ✔️ **5. Computer Players**

* Automated set scanning
* Fair and synchronized behavior
* Follows real-time timing rules

### ✔️ **6. Logging & Debugging Tools**

* `ThreadLogger` logs thread interactions
* Configurable log format & level
* Useful for debugging concurrency issues

### ✔️ **7. JUnit Tests**

Files:

* `PlayerTest.java`
* `TableTest.java`

Covers:

* Player behavior
* Set selection mechanics
* Table integrity
* Valid set detection

---

## 📂 **Project Structure**

```
├── Main.java
├── Env.java
├── Config.java
├── Dealer.java
├── Player.java
├── Table.java
├── Util.java
├── UtilImpl.java
├── InputManager.java
├── logger/
│   └── ThreadLogger.java
├── ui/
│   ├── UserInterface.java
│   ├── UserInterfaceSwing.java
│   ├── UserInterfaceDecorator.java
│   └── WindowManager.java
├── tests/
│   ├── PlayerTest.java
│   └── TableTest.java
└── config.properties
```

---

## 🧠 **How the Game Works (High-Level Flow)**

1. `Main` loads `config.properties`
2. Initializes:

   * Environment (`Env`)
   * UI (`UserInterfaceSwing`)
   * Table
   * Players (threads)
   * Dealer (thread)
3. Dealer:

   * Starts the game timer
   * Deals cards to table
   * Manages hints & reshuffles
   * Processes sets submitted by players
4. Players:

   * Search for sets continuously
   * Submit selections
   * Freeze on penalty or correct set
5. Game runs until:

   * Deck is empty
   * No more sets
   * Timer expires

---

## 🕹️ **Running the Game**

### **Compile**

```bash
javac *.java ui/*.java logger/*.java
```

### **Run**

```bash
java Main
```

The game opens a graphical window and begins automatically.

---

## 🧪 **Testing**

JUnit tests are included for core logic:

```bash
javac -cp .:junit-4.13.jar *.java test/*.java
java -cp .:junit-4.13.jar org.junit.runner.JUnitCore PlayerTest TableTest
```

---

## **In a Nutshell**

What was implemented:

* Full multithreaded architecture (dealer + players)
* Card logic, table logic, and set-validation rules
* Concurrency-safe communication between threads
* Swing GUI with decorators and visual effects
* Configuration system + environment class
* Logging utilities
* Game loop, player freeze logic, and scoring system
* Unit tests for key functionality

This project demonstrates:

✔ Java multithreading
✔ GUI programming
✔ OOP & design patterns
✔ Concurrency control
✔ Event-driven architectures
✔ Testing & debugging complex systems

---

## 📜 **License**

This project is intended for educational and portfolio use.
