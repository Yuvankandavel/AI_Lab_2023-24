# Ex.No: 3  Implementation of Minimax Search
### DATE:27/08/2025                                                                            
### REGISTER NUMBER : 212223060315
### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

### Program:
import math

def minimax(depth, node_index, is_max, scores, h):
    if depth == h:
        return scores[node_index]
    
    if is_max:
        return max(
            minimax(depth + 1, node_index * 2, False, scores, h),
            minimax(depth + 1, node_index * 2 + 1, False, scores, h)
        )
    else:
        return min(
            minimax(depth + 1, node_index * 2, True, scores, h),
            minimax(depth + 1, node_index * 2 + 1, True, scores, h)
        )

if __name__ == "__main__":
    scores = [3, 5, 2, 9, 12, 5, 23, 23]   # Leaf nodes
    h = math.log2(len(scores))             # Height of tree
    
    optimal_value = minimax(0, 0, True, scores, int(h))
    print("The optimal value is:", optimal_value)

### Output:
The optimal value is: 12



### Result:
Thus the optimum value of max player was found using minimax search.
