# Snake
Implement the classic Snake game in which a snake travels through a matrix at a direction which can be adjusted with the arrow keys, and must avoid colliding with the matrix walls or with itself. On its way, it can collect food which makes it grow longer.

### Data Model
use a 15 x 15 matrix of `cell` objects to model the board -

```js
{
	cellType: FLOOR | WALL,
	cellContent: SNAKE | FOOD | EMPTY,
}
```

use an array of  `position`  objects to model the snake

```js
{
	i: 3,
	j: 7,
}
```

### Game Rules

1. The snake has an initial length of 4 cells and starts with its head at the center of the board heading in a random direction (up, down, left or right).
2. The snake's direction can be changed by the arrow keys - if the snake is moving up or down, it can only be changed to either left or right and visa versa.
3. An interval advances the snake one cell in its current direction - the first cell of the snake (the head) moves in the current direction and each following cell takes the place of the cell which was in front of it. A simple way to achieve this is by removing the snake's last cell (the tail) cell and adding a new cell after its head.
4. If by advancing the snake collides with the board walls or any part of its own body, the game ends.
5. Another interval places food items at random empty cells every 10 seconds. When the snake "eats" the food, it grows one cell longer.

### Implementation Steps

1. Start by initializing the model and rendering the opening scene using a dynamically built HTML table. Use different colors for board walls, board cells,  the snake's body and the snake's head.
2. Initialize an interval to start advancing the snake. 
   *It may be useful to add a  button to toggle the interval for development purposes.*
3. Add collision detection (when the snake collides with a wall or itself).
4. Add navigation with the arrow keys. Use the provided starter code for hints on how to do this.
5. Add an interval for placing food in random empty cells every 10 seconds. To do this, use a function which adds the positions of all empty cells on the board into an array and draws a random one.
6. Implement the "eating" behavior of the snake. This is done by extending the snake's body into the cell with the food without trimming the tail cell.
7. Add a timer which will display `mm:ss` time since the game started.
8. Add and display a score which will be calculated as follows:
	1. Add `1 x snakeLength`  points every second.
	2. Add 1,000 points every time the snake eats food.

### Bonus Features

1. Each time another 10,000 points are scored, the game difficulty is increased by accelerating the interval. Change the game colors to give some more visual cues when this happens.
2. The user can pause the game by hitting the Esc key. When the game is paused, the timer is paused, and the board is rendered with no contents. Hitting Esc again re-renders the board and resumes the game play.
3. Add a Game Over modal with a restart button.

