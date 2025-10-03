# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE:  03/10/2025                                                                
### REGISTER NUMBER : 212223060315 
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### Steps:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:
```
MAX, MIN = 1000, -1000

def minimax(depth, nodeIndex, isMax, scores, alpha, beta, maxDepth):
    if depth == maxDepth:
        return scores[nodeIndex]

    if isMax:
        best = MIN
        for i in range(2):
            val = minimax(depth + 1, nodeIndex * 2 + i, False, scores, alpha, beta, maxDepth)
            best = max(best, val)
            alpha = max(alpha, best)
            if beta <= alpha:
                break
        return best
    else:
        best = MAX
        for i in range(2):
            val = minimax(depth + 1, nodeIndex * 2 + i, True, scores, alpha, beta, maxDepth)
            best = min(best, val)
            beta = min(beta, best)
            if beta <= alpha:
                break
        return best

if __name__ == "__main__":
    maxDepth = 3
    scores = [3, 5, 6, 9, 1, 2, 0, -1]
    bestValue = minimax(0, 0, True, scores, MIN, MAX, maxDepth)
    print("The optimal value for MAX player is:", bestValue)

```
### Output:

The optimal value for MAX player is: 5

### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
