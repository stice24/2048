# 2048



**Core Concepts**


- 2D arrays are used to create the 4x4 grid used to represent the game board.
- I initially had made a localized Tile class where they get and set their own
  colors and move themselves, but turned to using constant space for more efficiency

  I definitely tweaked my data structure plan the most, as it started as a collection
  that was a LinkedList of Maps carrying movement and distance of movement. This was
  overcomplicated, so I stuck with LinkedList, but adjusted to incorporate
  storage of my 2d array, which made it a lot easier to get my undo() function and much more
  working!

  File I/O: Similar to the functionality of testable, this also helped me analyze progress along the
  way. This is critical in save/load functions

**Implementation**


- GameBoard: Presents the local state of a board. The class builds the GUI representation of 2048
and provides KeyListener attributes that affect the board
It is the primary control center for relaying information to the model, Tommy 2048...


- Tommy2048: Pulls together the state defined by GameBoard and its implementations and edits the general state of
the game through manipulation of board movements, writing and reading movement/scoring progress, and tracking
move-by-move user choices to allow for supplemental features like undo, save, reset, and load.
RunTommy2048: Sets the initial state of the game by creating the file where progress is being tracked,
starting up and focusing the program GUI, and providing the notifiers and MouseListeners key to communicating
parts of the game such as instructions, the added controls, and game state.



- Design: I split up
  model code in 2048 from action listening and more small scale GUI drawing in GameBoard, which is also
  abstracted GUI-wise from RunTommy2048, as that took care of more broader state controls. This in turn
  allowed me to encapsulate private state, especially in board state tracking.
  I actually figured this out in testing which I explain above. That being said, if I could change anything,
  I'd do more GUI testing to find where I can more efficiently incorporate encapsulation to ensure
  all of my separated variables move smoothly as one.
