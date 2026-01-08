# 🧠 MazeMind 2D – Ultimate Edition

> **A self-adapting, intelligent maze where the game learns from the player.**

**MazeMind 2D** is an AI-powered maze simulation that goes beyond traditional gameplay.  
It introduces a **Dungeon Master AI** that continuously observes player performance and dynamically modifies the maze using **Reinforcement Learning (Q-Learning)** to maintain the perfect balance between challenge and fun.

🎯 Every run is unique.  
🧩 Every decision matters.  
🤖 The maze adapts—just like a smart system should.

## 🎮 Core Gameplay

The objective is simple:  
**Guide the robot to the exit (blinking door).**

⚠️ **But the maze is alive.**  
Walls shift, traps appear, and the AI responds to how well (or poorly) you play.

---

## 🌟 Key Features

- **🧱 Living Maze Environment**  
  Dynamic wall shifting ensures no two playthroughs are the same.

- **🌉 Bridge Builder Algorithm**  
  A graph-theory based safety mechanism guarantees that a valid path to the exit *always exists*.

- **🤝 Mercy Rule**  
  If a player struggles for more than 60 seconds, the AI assists by removing obstacles and traps.

- **🌫️ Fog of War**  
  Limited visibility simulates real-world robotic sensor constraints, increasing realism.

---

## 🤖 Agent Modes

MazeMind 2D supports **three intelligent interaction modes**:

### 1️⃣ Human Player (User-Controlled)
- Navigate using **Arrow Keys**
- Performance metrics tracked:
  - Time taken
  - Wall collisions
  - Trap encounters
  - Coins collected
- These metrics directly influence the difficulty of the next level.

---

### 2️⃣ A* Solver (Omniscient Agent)
- Full-map visibility (God Mode)
- Uses **A\*** Pathfinding Algorithm
- **Heuristic:** Manhattan Distance
- Always finds the shortest safe path to the goal.

---

### 3️⃣ AI Explorer (Autonomous Robot)
- No prior map knowledge
- Builds an internal **memory grid** while exploring
- Uses:
  - Frontier-based exploration
  - Dead-end detection and learning
  - Intelligent backtracking to least-visited cells
- Mimics real-world autonomous robot behavior.

---

## 🧠 Dungeon Master AI (Adaptive Controller)

A background AI agent manages the **difficulty balance** of the game.

### 🎯 Q-Learning Design

#### States (Input):
- **Fast** – Level completed in under 30 seconds
- **Medium** – Completion between 30–60 seconds
- **Slow** – Took over 60 seconds or Mercy Rule triggered

#### Actions (Output):
- Increase difficulty
- Maintain current difficulty
- Decrease difficulty

---

### 🔄 Feedback Loop
1. Player completes a level  
2. AI evaluates performance  
3. Q-Table is updated  
4. Next level is generated accordingly  

This creates a **self-learning game environment**.

---

## 🛠️ Technical Implementation

### 🔗 Graph Connectivity & Safety Check
To prevent impossible mazes:
1. Wall placement is simulated
2. BFS flood-fill checks start-to-end connectivity
3. If broken, the **Bridge Builder** restores a valid path automatically

---

## 🧪 Tech Stack

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

- **Rendering:** HTML5 Canvas (Pixel-perfect)
- **Styling:** Tailwind CSS (Modern UI & Glassmorphism)
- **Animations:** GSAP
- **Logic:** Pure JavaScript (No external game engines)

---

## 📄 License
This project is licensed under the **MIT License**.  
See the `LICENSE` file for details.

---

✨ *Built with curiosity, logic, and a love for intelligent systems.*
