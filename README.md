# sudoku
Sudoku board viewer and solver in IPython/Jupyter, using [NumPy](http://www.numpy.org/) arrays

View the notebook on [Github](https://github.com/marwahaha/sudoku/blob/master/solver.ipynb) or [nbviewer](http://nbviewer.ipython.org/github/marwahaha/sudoku/blob/master/solver.ipynb).
Forks and comments are welcome!

##Controls
###Reset
```bd = Board()``` will instantiate a new Sudoku board
###View
```bd.view()``` will return a copy of the current Sudoku board (as a NumPy array). The value "0" is unknown.
###Adding/Removing Values
```bd.set_val(val,pos)``` will put a value at position (either tuple (row,col) or int from 1 to 81). Position is indexed from 1. If value is not nonzero, then sets to "0" (unknown). A full list of commands is here:
```
bd.set_board(vals)      #expects len(vals) == 81
bd.set_row(vals,row)    #expects len(vals) == 9; row is int from 1 to 9
bd.set_column(vals,col) #expects len(vals) == 9; col is int from 1 to 9
bd.set_val(val,pos)     #expects len(pos) == 1 (int from 1 to 81) or 2 (tuple with row and column indices)
```
###Checking Board
```bd.check_solved()``` will check if the Sudoku board is complete. ```bd.check_legal()``` will check if the entries on the board are legal. A full list of checks are here:
```
bd.check_solved()       #board solved?
bd.check_filled()       #board has all nonzero entries?
bd.check_legal()        #board has all legal entries?
bd.check_rows()         #for each row, is each nonzero entry distinct?
bd.check_columns()      #for each col, is each nonzero entry distinct?
bd.check_boxes()        #for each box, is each nonzero entry distinct?
```
###Solving
```bd.solve()``` will attempt to solve the board (brute-force) with its given entries. On completion, the procedure will print its status (success or failure). If failure, the procedure has no effect. (This is a brute-force solver, but it is reasonably fast for many boards)
##Have fun!
Let me know if there are any bugs or comments. Enjoy :-)
