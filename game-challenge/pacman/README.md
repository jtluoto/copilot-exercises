# Pacman: The Ghost-Busting Game Challenge

This folder contains example prompts on how to create the classic Pacman game and the source code for the game that was generated using the prompt listed in this README.md. The game uses JavaScript but the same prompts can be used for any programming language. Use the prompts as an inspiration for your own Copilot assisted implementation. You can use the graphics in the assets folder or use your own.

## Prompting the Pacman game

### Phase 1: The essentials

1. Chat: I want to make a Pacman game that is running in a browser. Which programming language you suggest?
2. Chat: Is React or plain JavaScript better for this purpose?

3. Chat: Use Javascript and Phaser to create a Pacman game. The playing area will be on the left side of the screen and it will take 80% of the width of the screen. The right side of the screen will be 20% of the width of the screen and there will be the points the player has received. The whole background of the screen will be black. The playing maze is a square and will be on the playing area side. The player can move Pacman in the maze. The maze has small dot's that the Pacman can eat and receive points. Locations of the walls are defined in maze.json file. All images are in assets folder. Set velocity value into a variable.

- Note! Check that the filenames of the images are correct!
- Fix also the layer names if needed, open from browser the console to see the errors

4. Chat: How can I create the maze where the Pacman is moving?

5. Chat: The dots should be placed to each tile where there is no wall in it. Add dots by going through the walls layer
   and place a dot on each tile where there is no walls

6. Chat: How can I now run the app?

```
npm install -g http-server
cd /path/to/your/project
http-server
```

7. Chat: The dots are now quite big, can you make the dots smaller? Dots could be 30% of the size it is now

8. Pacman seems to be too big. Chat: "Adjust player size to 80% of the original size"

9. Chat: Load ghost image

### Phase 2: Adding the missing bits and pieces

A lot of comments were used in this phase to generate code in specific parts of the codebase. Add a comment and Copilot will suggest code matching the comment.

1. Added variables ghosts, ghosthome, ghostdoor, directions, and tileSize=32 manually
``` 
// Add moving directions to an array. Direction can be up, down, left and right, but use numbers for x and y

let directions = [
    { x: 0, y: -1 }, // Up
    { x: 0, y: 1 }, // Down
    { x: -1, y: 0 }, // Left
    { x: 1, y: 0 } // Right
];
```

2. Added values to the variables in the create()-function manually. Added the following comments in the create() functions and accepted Copilot's suggestion based on them:
"Define ghosthome area and where is the door to the ghosthome by using the tileSize. Ghosthome is in the middle of the maze"
"Ghostdoor is in top of the ghosthome area in the middle of the edge of the area"
- Check that the values are correct:
- ghosthome = new Phaser.Geom.Rectangle(12 * tileSize, 12 * tileSize, 5 * tileSize, 3 * tileSize);
- ghostdoor = new Phaser.Geom.Rectangle(14 * tileSize, 11 * tileSize, 1 * tileSize, 1 * tileSize);

3. Chat: Do not add dots to ghosthome area
- May not work at one shot, paint the code and tell in the chat that this is not working
- May still need to be fixed by hand

4. Continued in create()-function by adding a comment: "Create ghosts so that they will spawn to their ghosthome area next to eachother into two rows. Create four ghosts and set its size to 10% of the original size of the ghost image. Use tileSize when positioning the ghosts to make sure they are next to eachother"

5. Added comment "Add collider between ghosts and pacman. Ghosts will eat the player if they collide and eatPacman will be called"

6. Started to write function **eatPacman** in the end of the file and implement the eatPacman-function
- Added comment "Reset the position of player" should produce code: pacman.disableBody(true, true);
- There should be also a code for reseting the score
- Chat: "Add a notification to the user that the game is over and ask to play again.
  Create first the notification and then add a button into the notification to play again.
  There is a box around the notification and the button. Button's bachground is black and text is white.
  Place the notification box to the middle of the screen"
- Chat: "The styling should be in styles.css file"
- Add comment to button click handler: "Restart the game". Code added should be game.scene.start("pacman"); and also a key field with value "pacman" should be added to scene variable.

7. **Colliders**: Went to the end of the create()-function and added a comment "Add collider between the ghosts and the walls. When a ghost hits a wall, change it's direction randomly in the collider function". Moved walls variable out from the function.

8. Added a comment in create()-function: "Add collider between the ghosts and ghosts. When a ghost hits another ghost, change their direction to opposite direction in the collider function"

9. **Ghosts moving**: Add comment to end of update() function: "Move ghosts towards ghostdoor if they are inside the ghosthome. If they are outside the ghosthome, move them randomly"

10. The ghosts blocked the ghosthome door. Added comment to the ghosts moving code inside the condition that the ghost is in the ghosthome: "At 10% probability, change the direction of the ghost towads the pacman"

11. **Winning the game**: Added to eatDot a comment: "When all dots are eaten, the game is over and the player wins"

### Phase 3: Fine-tuning
1. Chat: How can I write test cases to this application?
2. Chat: Could you refactor the code so that all ghosts related code is in separate file?
3. Chat: Explain the code 
1. Chat: Create Dockerfile
2. Chat: How to run the app in container
3. Chat: Create documentation to a README.md-file
4. Chat: Is my code secure?
