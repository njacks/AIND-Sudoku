# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked twins is used as a strategy to reduce the number of possibilities for boxes in a sudoku puzzle. By finding a pair of boxes belonging to the same set of peers with the same pair of digits, we can eliminate the two digits from all other peers of the naked twins.
   By grouping all boxes that only have two digits, then further grouping like boxes into pairs gives us naked twins. The digits in the naked twins are then removed from all peers of both twins. By using this constraint iteratively, the sudoku puzzle can be reduced to fewer possibilities.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: This can be achieved by including the diagonal constraint as another unit in the sudoku puzzle. This results in all boxes included in the main diagonals to having all of the main diagonal boxes as peers. Hence, solutions that do not satisfy the constraint are rejected.

```python
diagonal_units = [[rows[i]+cols[i] for i in range(len(rows))]] + [[rows[i]+cols_reversed[i] for i in range(len(rows))]]

unitlist = row_units + column_units + square_units + diagonal_units
```

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.