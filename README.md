# Sudoku Solver

A new DS project using Back tracking Algo.

## Installation

You can clone by copy and pasting below commands in your Terminal.

```bash
    git clone https://github.com/darshn-n/sudoku-solver/
    cd sudoku-solver
    flutter run
```

Project Folder Structure

```
📦SUDOKU-SOLVER
 ┣ index.html
 ┣ sudoku.js
 ┣ logo.png
```

Pre-Requisites

```
* Basic Knowledge of html
* Need Expert Skills of Algorithms.
* Intermediate JS Knowledge.
```

## Introduction

Probably you might know what sudoku is or might have heard somewhere about it.Let's begin with a brief note on it.

Sudoku is a logic based number placement puzzle.

Given a 9×9 grid, with some initial values filled.The objective is to fill all the empty cells of the grid with numbers such that it becomes valid.

## Backtracking

Backtracking is a kind of brute-force approach which comes into picture when solving a problem requires considering multiple choices as we don't know which choice is correct and we try to solve the problem using trail and error method considering one choice at a time until required answer is obtained.

Sudoku can be solved in the way mentioned above.

The difference between brute-force and backtracking is that in backtracking, we do not explore all the possible options instead we explore only worthy options and build the solution incrementally.

## Grid

1.Find an unfilled cell (i,j) in grid
2.If all the cells are filled then
  2.1. A valid sudoku is obtained hence return true
3.For each num in 1 to 9
  3.1. If the cell (i,j) can be filled with num then fill it with num temporarily to check
  3.2. If sudokuSolver(grid) is true then return true
  3.3. If the cell (i,j) can't be filled with num the mark it as unfilled to trigger backtracking
4.If none of the numbers from 1 to 9 can be filled in cell (i,j) then return false as there is no solution for this sudoku

## Steps

-We start by finding an unfilled cell(i,j).
-If all the cells are filled then a valid sudoku is obtained.
-We try to place every number between 1 to 9 in the unfilled cell.
-Before placing we check for the constraints by checking the current row,current column and current 3×3 submatrix.
-If any of the any of the constraint becomes false we'll not place that number at (i,j).
-If all the constraints are true then we'll place that number at (i,j) and then repeat the process by finding an unfilled cell.
-If at any point none of the numbers can be placed at (i,j) then we've to backtrack and change the values for already visited cells

To check the 3×3 submatrix(box) condition

Find the center cell using the following
r=(row//3)×3+1  c=(col//3)×3+1
For example take (5,6),
r=(5//3)×3+1=1×3+1=3+1=4
c=(6//3)×3+1=2×3+1=6+1=7
Hence the center cell for box containing (5,6) is (4,7)

After finding the center cell it easy to check as all the values in the box will be at unit distance from the center cell.

Let's look at the algorithm.

## Time and Space Complexity

Consider there are m unfilled cells in the sudoku

Time Complexity:

The backtracking algorithm takes O(9m) time complexity in the worst case since for every unfilled cell there are 9 possibilites to explore and there are m unfilled cells in the sudoku.

Worst Case Time Complexity: O(9m)
Average Case Time Complexity: O(9m)
Best Case Time Complexity: O(m2) [This takes place when the number of backtracking steps are minimized]
For Brute force approach:

Worst Case Time Complexity: O(9m)
Average Case Time Complexity: O(9m)
Best Case Time Complexity: O(m)
Note, in the best case, Brute force approach performs better than Backtracking approach. Despite same Time Complexity for average and worst case, the exact number of steps in Backtracking approach is much less and hence, is an efficient approach to solve Sudoku.

Space Complexity:

At most, there can be m function calls in the recursion stack. Hence the space complexity would be O(m).

## Conclusion

Other ways to solve sudoku are:

Crook’s algorithm
Constraint programming
AI based approach
With this article at OpenGenus, you must have the complete idea of Backtracking Algorithm for Sudoku.

### That's it

```
 Voila
```
