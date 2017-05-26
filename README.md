# kixote
A puzzle generator - another Javascript learning project.

The kixote repo contains pages that display interactive *path puzzles* based on the moves of chess pieces, and the utilities that generate them.

A path puzzle is built from a numbering of the squares on a chess board. The numbering corresponds to a path taken by a particlar type of chess piece (different pieces for different puzzle types) as it moves over the whole board, landing on each square exactly once. In creating a path puzzle, once the all the squares are numbered, a certain amount of the numbers are hidden. 

Someone solving the puzzle is tasked with filling in the missing numbers to re-discover the original path. In the interactive version here, the solution must be provided in sequential order. The solver can look ahead, but at each turn can only fill in the next empty cell in the sequence, tracing over the path originally followed by the chess piece.

There are three kinds of puzzles here:
* *kixote* - path puzzles based on a knight's tour;
* *hidato* - path puzzles based on a king's tour'
* *numbrix* - path puzzles based on a tour generated by a non-standard piece that can move up, down, left and right.

There is also a knight's tour generator page that allows the user to experiment with creating their own knight's tours.

The mechanics of generating puzzles is the same for all types.
1. Randomly choose a square on the board to start on. 
2. Generate a tour of the chessboard using the particular piece type. The mechanism used is the "Warnsdorff" heuristic, which generates paths by always selecting the next square from among those that have the least number of free moves from them. This is not guaranteed to always create a tour, so more than one attempt may be required when generating the path.
3. Hide a certain number of squares. Currently the placement and number of hidden squares is done following rules that were arrived at through experiment. 
4. Submit the puzzle to an automatic puzzle solver, which will find all solutions for the puzzle.
5. If more than one solution to the puzzle is found, reveal one of the hidden squares that occured at a 'branch point' of the different solution paths. Repeat step 4.
6. When a single solution remains for the puzzle, display the puzzle to the user.

I started looking at puzzles like this a few years back. Some background on these can be found on these blog posts:
* [Hidato or a King's Tour](http://www.mathrecreation.com/2011/06/hidato-or-kings-tour.html)
* [Kixote or Knight's Path Puzzles](http://www.mathrecreation.com/2011/06/kixote-or-knights-path-puzzles.html)

For even more background, see these posts:
* [Life Lessons from a Knight's Tour](http://www.mathrecreation.com/2016/12/life-lessons-from-knights-tour.html)
* [Build Your Own Knight's Tour](http://www.mathrecreation.com/2017/01/build-your-own-knights-tour.html)

See [dmackinnon1.github.io/kixote/](http://dmackinnon1.github.io/kixote/) for links to a live example of the various puzzle types.
