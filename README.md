# 🧠 MazeMind 2D - Ultimate Edition

> **A self-adapting, living maze environment where the game learns from you.**

**MazeMind 2D** is not just a maze game; it is an AI simulation sandbox. It features a **"Dungeon Master" AI** that uses Reinforcement Learning (Q-Learning) to analyze your performance in real-time and adjust the maze's difficulty, layout, and traps dynamically.

[Click here to play the game!](https://aiswaryajosy.github.io/MazeMind/)


## 🎮 The Core Experience

The goal is simple: Navigate the robot to the exit (blinking door). 
**The challenge?** The maze fights back.

### 🌟 Key Features
* **Living Environment:** Walls shift and move while you play.
* **Bridge Builder Algorithm:** A graph-theory safety check ensuring that no matter how walls shift, a path to the exit *always* exists.
* **Mercy Rule:** If a player gets stuck for more than 60 seconds, the AI intervenes, breaking down walls and removing traps to assist you.
* **Fog of War:** Simulate limited sensor visibility for a true exploration challenge.


## 🤖 The Agents (Modes)

MazeMind 2D features three distinct ways to interact with the environment:

### 1. Human Player (The User)
You control the agent manually using `Arrow Keys`. The system tracks your:
* **Time taken**
* **Wall collisions**
* **Trap falls**
* **Coins collected**
This data is fed into the Q-Learning algorithm to determine the difficulty of the *next* level.

### 2. A* Solver (The Omniscient)
This agent has "God Mode" vision. It sees the entire map instantly.
* **Logic:** Uses the **A* (A-Star) Pathfinding Algorithm**.
* **Heuristic:** Manhattan Distance.
* **Behavior:** It calculates the mathematically shortest path avoiding all walls and traps and executes it perfectly.

### 3. AI Explorer (The Robot)
This is an autonomous agent simulating a real robot with no prior knowledge of the map.
* **Memory Grid:** It builds an internal map (`aiMemoryGrid`) as it moves. It remembers where walls, traps, and open spaces are.
* **Frontier Exploration:** It identifies "unknown" areas adjacent to "known" areas and prioritizes exploring them.
* **Dead-End Learning:** If it detects it is surrounded by 3 walls, it marks that tile as a "virtual wall" so it never backtracks there unnecessarily.
* **Smart Backtracking:** When stuck, it calculates the path to the least-visited accessible tile.


## 🧠 The "Maze Master" (Dungeon Master AI)

The game is controlled by a background AI agent that manages the fun factor.

### Q-Learning Architecture
The Maze Master uses a **Q-Table** to make decisions based on States and Actions.

* **States (Input):**
    * `Fast`: The player finished too quickly (< 30s). The game is too easy.
    * `Medium`: The player finished in a normal time (30s - 60s).
    * `Slow`: The player struggled (> 60s) or triggered the Mercy Rule.
* **Actions (Output):**
    * `Increase Difficulty`: Adds more traps, denser walls, and faster wall shifting.
    * `Keep Difficulty`: Maintains current settings.
    * `Decrease Difficulty`: Removes traps, simplifies maze structure, slows down shifting.

### The Feedback Loop
1.  You play a level.
2.  The AI evaluates your performance score.
3.  The AI updates its **Q-Table** (Memory) to learn which action results in the best game balance.
4.  The next level is generated based on this decision.


## 🛠️ Technical Implementation Details

### Graph Connectivity & The "Bridge Builder"
When the environment is set to **Dynamic**, the maze shifts walls randomly. To prevent the player from getting trapped in an impossible box, the code runs a connectivity check:
1.  It attempts to place a wall.
2.  It runs a flood-fill algorithm (BFS) to see if the Start is still connected to the End.
3.  If the path is broken, the **Bridge Builder** identifies candidate walls that separate the "Start Set" from the "End Set" and breaks one open to restore the path.

### Tech Stack

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

* **Rendering:** HTML5 Canvas API (Pixel-perfect rendering).
* **Styling:** Tailwind CSS for the HUD and Glassmorphism effects.
* **Animation:** GSAP (GreenSock) for smooth UI transitions and camera shakes.
* **Logic:** Vanilla JavaScript (No external game engines used).

## 📄 License
Distributed under the MIT License. See `LICENSE` for more information.
