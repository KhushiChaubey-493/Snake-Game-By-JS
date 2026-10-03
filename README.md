# 🐍 Snakemia – Ek Gaming Katha

A classic **Snake Game** built using **HTML, CSS, and JavaScript**. The game features real-time score tracking, persistent high-score storage, keyboard controls, collision detection, randomly generated food, and sound effects.

The project was created to practice **JavaScript game logic, DOM manipulation, keyboard event handling, animation loops, collision detection, and browser local storage**.

---

## 🎮 Live Demo

**Play the game:**
https://khushichaubey-493.github.io/Snake-Game-By-JS/

---

## 📌 Overview

**Snakemia** is a browser-based implementation of the classic Snake game.

The player controls the snake using the **Arrow Keys**, collects food to increase the score and snake length, and must avoid colliding with the walls or its own body.

The game also stores the player's highest score in the browser using `localStorage`, allowing the high score to remain available between sessions.

---

## ✨ Features

* 🐍 Classic Snake gameplay
* 🎯 Food collection
* 📈 Real-time score tracking
* 🏆 Persistent high-score tracking
* ⌨️ Arrow-key controls
* 💥 Wall collision detection
* 💥 Self-collision detection
* 🍎 Random food generation
* 🔊 Food collection sound
* 🎵 Background music
* 💀 Game-over sound
* 🔄 Game restart after collision
* ⚡ Browser-based gameplay
* 💾 High score stored using `localStorage`

---

## 🛠️ Technologies Used

| Technology                  | Purpose                                     |
| --------------------------- | ------------------------------------------- |
| **HTML5**                   | Game structure and score display            |
| **CSS3**                    | Game board, snake, food, and visual styling |
| **JavaScript (ES6+)**       | Game logic and interaction                  |
| **DOM Manipulation**        | Dynamically rendering snake and food        |
| **Web Audio API / Audio**   | Game sounds and background music            |
| **localStorage**            | Persistent high-score storage               |
| **requestAnimationFrame()** | Game loop and movement timing               |

---

## 📂 Project Structure

```text
Snake-Game-By-JS/
│
├── music/
│   ├── background.mp3
│   ├── foodSound.mp3
│   ├── gameOverSound.mp3
│   └── moveSound.mp3
│
├── index.html
├── script.js
├── style.css
├── Snakemia_Screenshot.png
└── README.md
```

---

## 🎮 How to Play

1. Open the game in your browser.
2. Press any **Arrow Key** to start moving the snake.
3. Use:

   * `↑` — Move Up
   * `↓` — Move Down
   * `←` — Move Left
   * `→` — Move Right
4. Move the snake toward the food.
5. Eating food increases your score and makes the snake longer.
6. Avoid:

   * The walls
   * The snake's own body
7. If a collision occurs, the game ends and can be started again.

---

## ⚙️ How the Game Works

### 1. Game Board

The HTML contains a dedicated game-board container:

```html
<div class="game-board"></div>
```

JavaScript dynamically creates the snake and food elements and places them on the CSS grid.

---

### 2. Snake Representation

The snake is represented using an array of coordinate objects:

```javascript
let snakeArr = [{ x: 13, y: 15 }];
```

Each object represents the position of one segment of the snake.

As the snake grows, additional coordinate objects are added to the array.

---

### 3. Movement

The snake's movement is controlled using an `inputDirection` object:

```javascript
let inputDirection = { x: 0, y: 0 };
```

Arrow-key events update the direction:

```text
Arrow Up     → y = -1
Arrow Down   → y =  1
Arrow Left   → x = -1
Arrow Right  → x =  1
```

The snake's head position is then updated according to the current direction.

---

### 4. Game Loop

The game uses:

```javascript
window.requestAnimationFrame(main);
```

The `main()` function repeatedly runs the game loop and controls when the next game update should occur.

The current implementation uses a `speed` value to determine the movement interval.

---

### 5. Food Generation

When the snake reaches the food:

```javascript
if (snakeArr[0].y === food.y && snakeArr[0].x === food.x)
```

the game:

* Increases the score.
* Plays the food sound.
* Extends the snake.
* Generates a new random food position.
* Updates the high score if necessary.

---

### 6. Collision Detection

The `isCollide()` function checks two major collision conditions.

#### Self Collision

The snake's head is compared with the remaining body segments.

If the head occupies the same position as another segment, a collision occurs.

#### Wall Collision

The game also checks whether the snake's head moves outside the playable grid boundaries.

A collision triggers the game-over logic.

---

## 🏆 Score & High Score

The game maintains two values:

```javascript
let score = 0;
let highScoreValue = 0;
```

The score increases by **1** whenever the snake eats food.

The high score is stored in browser `localStorage`:

```javascript
localStorage.setItem(
    "highScore",
    JSON.stringify(highScoreValue)
);
```

When the page is loaded again, the previously stored high score is retrieved and displayed.

---

## 🔊 Sound Effects

The project includes several audio files:

* `foodSound.mp3` — played when food is collected.
* `gameOverSound.mp3` — played after a collision.
* `moveSound.mp3` — included for movement audio.
* `background.mp3` — background music during gameplay.

The sounds are loaded using JavaScript's `Audio` object.

---

## 🧠 JavaScript Concepts Practiced

This project provides practical experience with:

* Variables and objects
* Arrays
* Functions
* Conditional statements
* Loops
* Event listeners
* Keyboard events
* DOM manipulation
* Dynamic element creation
* CSS Grid positioning through JavaScript
* `requestAnimationFrame()`
* Collision detection
* Random number generation
* `localStorage`
* Browser audio
* Game-state management

---

## 📸 Project Screenshot

The repository includes a project screenshot:

```markdown
![Snakemia - Ek Gaming Katha](Snakemia_Screenshot.png)
```

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/KhushiChaubey-493/Snake-Game-By-JS.git
```

### Navigate to the Project

```bash
cd Snake-Game-By-JS
```

### Run the Game

Open `index.html` in a modern web browser.

No backend, database, package manager, or build process is required.

---

## 🌐 Browser Compatibility

The project uses standard browser technologies including:

* HTML5
* CSS3
* JavaScript
* DOM APIs
* `localStorage`
* Browser audio
* `requestAnimationFrame()`

A modern browser such as Chrome, Edge, Firefox, or Safari is recommended.

---

## 🎯 Learning Objectives

This project was developed to practice:

* Building an interactive browser game
* Managing game state with JavaScript
* Implementing keyboard controls
* Working with arrays and coordinate systems
* Detecting collisions
* Generating random game objects
* Dynamically rendering elements
* Creating a continuous game loop
* Persisting data with `localStorage`
* Integrating sound into a JavaScript application

---

## 🔮 Future Improvements

Possible future enhancements include:

* Add a start/restart button instead of relying on keyboard input.
* Add pause/resume functionality.
* Add difficulty levels.
* Add increasing speed as the score grows.
* Add mobile touch controls.
* Add a dedicated game-over screen.
* Add multiple food types with different scores.
* Add obstacles or different game modes.
* Improve responsive behavior for mobile devices.
* Add a leaderboard.

---

## 📌 Project Status

**Status:** Completed

This is a frontend JavaScript game project created to practice game logic, DOM manipulation, keyboard interaction, browser storage, and audio integration.

---

## 👩‍💻 Author

**Khushi Chaubey**

GitHub:
https://github.com/KhushiChaubey-493

---

## 📄 License

This project is available for educational and personal use.
