# FIFTH PRACTICE INTELLIGENT SYSTEMS
# TIC TAC TOE

<p align="center">
  <img src="https://alfonsopinel.files.wordpress.com/2013/07/esquina-fallo-caso-1.gif" alt="Sublime's custom image"/>
</p>

## NAMES 📋
* Balderrama Mauricio
* Canedo Juan Luis
* La Fuente Mercedes

### DISCLAIMER
As a matter of time and security of the group, the work was done continuously and incrementally through a visual studio share in meetings that were scheduled according to the availability of each one, the continuous commit was not taken into account because we always worked as a group and we were not able to push, because everything was done in a single shared machine. 
Previously the separate work was taken into account but due to lack of coordination.  

### IMPORTANT! HOW TO USE :hammer:
* Clone from the main repository using: 

     -git clone (repository link)
* For the correct functioning of the code you first need to install numpy and matplotlib from the console with the following command:                   

     -pip install numpy

* Insert in the console terminal 'python main.py' to start the program

* The program at startup shows you the available agents with which you can start the game. 

* You must select two players

* The program will ask you for a board size which you have to enter taking into account that it must be greater or equal to 3
 
* The first player to be defined automatically will be set as X who will be the first to start the game and the second player as O.

* When it is your turn the program will ask you to enter a position which is defined by column and row (it is allowed to add as columns lowercase and uppercase letters that are within the range).

* When the program finishes it will show the result of the game and who won, it will also show the execution time that each agent had to make the decision and finally it will show the number of nodes expanded with each agent that is not human. 

* You will be allowed to play again and points will be added automatically in case you play more than one game. 

* The program generates a txt file in which it shows the times in which each action is executed regardless of whether it is from the program or a human.


## MIN MAX ALGORITHM

Minimax algorithm calculate the minimax decision at a current state and try to find the optimal move for a player, assuming that your opponent also plays optimally.
It use a backtracking-like method, doing a simple recursive call developping all leaf of the tree, pushing up these values level by level. Minimax explore (DFS Depth First Search) the tree.

Here is a visual exemple of how minimax works

<p align="center">
  <img src="https://user-images.githubusercontent.com/28982255/83515724-7975e880-a4f3-11ea-9630-a41f21d9a103.gif" alt="Sublime's custom image"/>
</p>

## ALPHA BETA PRUNNING ALGORITHM
1956, John McCarthy is presiding Dartmouth's conference, in which he presents alpha-beta prunning, that seeks to decrease the number of nodes that are evaluated by the minimax algorithm in its search tree. It stops evaluating a move when at least one possibility has been found that proves the move to be worse than a previously examined move. Such moves need not be evaluated further. When applied to a standard minimax tree, it returns the same move as minimax would, but prunes away branches that cannot possibly influence the final decision.

Visual explanation of alpha-beta prunning

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/4/49/Animation_of_alpha-beta_pruning.gif" alt="Sublime's custom image"/>
</p>

## DESCRIPTION OF HEURISTICS
The heuristic method of class Board assigns a value to a given board state based on the number of Xs and Os on the board in addition to the existing lines of Xs and Os that might indicate one player is closer to winning than another. Exact values are a result of trial-and-error. Heuristic values for each state are stored in additional cache in so that they needn't be calculated again.



## PROBLEM SOLVER AGENT ⚙️

### Objective Formulation:
Implement the intelligent N in dash (3, 4, 5 in dash) also known as tic-tac-toe with the algorithms MinMax, AlphaBeta Prunning and MinMaxCutof.

### Problem Formulation:


### Initial State:
A n*n size board that is empty

![STATEINITIAL](https://user-images.githubusercontent.com/74753713/136325399-eaab7f04-1196-405a-a1d7-c83f5a767ae1.png)


### Objective State:
The same board with a number and positioning of x or circles that define a winner or tie.  

![STATEEND](https://user-images.githubusercontent.com/74753713/136325485-62e1a101-43d5-4fa4-a1ac-ba0a9bd668b6.png)



### Test of Objective:
Can the program make an intelligent decision of where to put its x or circle so that it always wins or draws?

### Actions:
* Place an x or circle in an available position on the board. 




## DESCRIPTION OF THE PROBLEM
You must generate an intelligent program that allows you to analyze all possible states that are beneficial against a human opponent by implementing algorithms that will make it intelligent such as MinMax, MinMax + AlphaBeta Prunning.
and MinMaxCutOff 


## SOLUTION DESCRIPTION
The program allows to generate a board of dimensions n * n that are greater or equal to three, it also allows to choose if the first player will be human or the same program which has implemented the requested algorithms, the first player is always x whether it is the computer or human and also the program always looks for the best solution so that it wins or draws against its opponent.

The program uses several confrotation algorithms such as Min Max, Min max alpha betta prunning and Min max cutt off but additionally uses the existing heuristics of Zobrist Hashing which is a hash function that is widely used in 2-player board games. It is the most common hash function used in transposition table. Transposition tables basically store the evaluated values of previous board states, so that if they are encountered again, we simply retrieve the stored value from the transposition table. We will cover transpose tables in a later article. 




## EXPERIMENTS :round_pushpin:

### NOTES
Each experiment performed was done in an environment in which the two agents are the computer and the same algorithm. 

### 1. Number of expanded states, Execution time and Execution result for board 3x3

#### :arrow_down_small: Experiments and results:

##### Min Max Agent 


  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
  8.76531162 | 1.423083000006 | 557487 | 60688 | Draw
  7.72937368 | 1.1550937750045 | 1114974 | 121376 | Draw 
  8.19679900 | 1.0290801999992 | 1245897 | 157891 | Draw
  
  
  
 ##### Min Max Alpha Beta Prunning Agent 


  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
  0.008020860000000596 | 0.007300824999999733 | 819 | 578 | Draw
  0.007836479999999924 | 0.006701374999999565 | 1083 | 1156 | Draw
  0.004403000000000467 | 0.006689008333332931 | 1347 | 1734 | Draw
  
  
  ##### Min Max Cutt Off Agent 


  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
  0.0253612999999995 | 0.015399450000000314  | 468 | 256 | Draw
  0.01614534000000125 | 0.015588750000000928 | 633 | 512 | Draw 
  0.013093246666667764 | 0.015564358333334619 | 798 | 768 | Draw  
  


### NOTE 
The evaluation of the agent with only min max was not taken into account due to the excessive delay not only in execution time but also in computer memory resources to make a decision on a board larger than 3 X 3.

### 2. Number of expanded states, Execution time and Execution result for board 4x4

#### :arrow_down_small: Experiments and results:  
  
 ##### Min Max Alpha Beta Prunning Agent 


  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
   0.02465118750000006 | 0.020783462500000183 | 2932  | 2294 | Draw 
   0.01990927500000078 | 0.019110718750000977 | 5010 | 4588 | Draw 
   0.018342691666668205 | 0.018484245833333596 | 7088 | 6882 | Draw
  
  ##### Min Max Cutt Off Agent 


  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
  0.13512828749999994 | 0.09726290000000026 | 2567 | 2248 | Draw
  0.10862208124999972 | 0.09674043750000016 | 4534 | 4496 | Draw 
  0.10008275833333354 | 0.0970265624999999 | 6501 | 6744 | Draw 


### 3. Number of expanded states, Execution time and Execution result for board 5x5

#### :arrow_down_small: Experiments and results:

    
 ##### Min Max Alpha Beta Prunning Agent 

   
  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
   0.021876115384615424 | 0.021099149999999955  | 3281 | 3071 | Draw 
   0.019763750000001547 | 0.021189479166665654 | 6093 | 614 | Draw  
   0.01910204615384525 | 0.021263758333332036 | 8905 | 9213 | Draw
  
  ##### Min Max Cutt Off Agent 


  Run Time X (second) |  Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: 
  0.329658823076923 | 0.3123124 | 3608  | 3224 | Draw
  0.29569597307692325 | 0.31322052500000036 | 6526 | 6448 | Draw 
  0.282937802564102 | 0.31784044444444576 | 9444 | 9672 |  Draw


### 4. Algorithms Competition 3 x 3 

#### :arrow_down_small: Experiments and results:

  Algorithm I | Algorithm II | Run Time X Algorithm I (second) |  Algorithm II Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: | :---: | :---:
  Min max | Min Max Alpha Beta | 7.65047436 | 0.009880799999999464 | 557487 | 846 | Draw
  Min max | Min Max Cutt Off |  7.614115340000002 | 0.016792000000000584 | 557487 | 276 | Draw
  Min Max Alpha Beta | Min Max | 0.00991497999999993 | 1.0421006249999998 | 819 | 60688 | Draw
  Min Max Alpha Beta | Min Max Cutt Off | 0.007781800000000061 | 0.017066499999999873 | 819 | 278 | Draw
  Min Max Cutt Off | Min Max |  0.025543020000000017 | 0.98045015 | 468 | 56490 | Draw
  Min Max Cutt Off | Min Max Alpha Beta | 0.03147322000000017 | 0.010567324999999794 | 468 | 921 | Draw
  
### NOTE 
The evaluation of the agent with only min max was not taken into account due to the excessive delay not only in execution time but also in computer memory resources to make a decision on a board larger than 3 X 3.
 
### 5. Algorithms Competition 4 x 4 

#### :arrow_down_small: Experiments and results:

  Algorithm I | Algorithm II | Run Time X Algorithm I (second) |  Algorithm II Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: | :---: | :---:
  Min Max Alpha Beta | Min Max Cutt Off | 0.026708483333333238 | 0.13381676666666684 | 2415 | 2248 | O
  Min Max Cutt Off | Min Max Alpha Beta | 0.2380675000000001 | 0.03276520000000064 | 2061 | 1587 | X
  

### 6.  Algorithms Competition 5 x 5

#### :arrow_down_small: Experiments and results:

  Algorithm I | Algorithm II | Run Time X Algorithm I (second) |  Algorithm II Run time O (second) |  States Visited X | States Visited O | Winner
  :---: | :---: | :---: | :---: | :---: | :---: | :---:
  Min Max Alpha Beta | Min Max Cutt Off | 0.023586953846153672 | 0.32774024166666665 | 3608 | 3145 | Draw
  Min Max Cutt Off | Min Max Alpha Beta | 0.32351358461538465  | 0.05862593333333329 | 3394 | 9002 | Draw
  

### 7. Time Comparation Table
#### :arrow_down_small: Experiments and results:


![image](https://user-images.githubusercontent.com/74753713/136321836-f9a73971-14cb-4dcf-9097-315a5f0cd9d0.png)



### 8. Time Comparation Graphic 
#### :arrow_down_small: Experiments and results:

![image](https://user-images.githubusercontent.com/74753713/136321861-1f5a9362-5509-4e02-9dbf-79e8b8f32b36.png)


### 9. Nodes Expanded Comparation Table
#### :arrow_down_small: Experiments and results:


![image](https://user-images.githubusercontent.com/74753713/136322037-e78f6a43-4d52-4eda-8e5d-a8f07da64cde.png)




### 10. Nodes Expanded Comparation Graphic 
#### :arrow_down_small: Experiments and results:

![image](https://user-images.githubusercontent.com/74753713/136322074-6d132932-1b28-4e42-a7fe-9295003a3327.png)





## CONCLUSION
* The experiments carried out on the program and the execution of competitions between its agents show us that in terms of time the best execution is the Min Max Alpha Beta algorithm, likewise the worst performance is the Min Max that reaches five seconds, graphically it can be seen that if you start with the Min Max algorithm the execution time rises out of the normal due to the expansion of all possible states, Theoretically the cut off algorithm is more optimal than alpha and beta but in our implementation due to all the processes behind it the use of Zobrist Hashing could slow down the total execution time. 

* The number of expanded states is fundamental for the good performance of a program in the table of comparisons of expanded states of the intelligent agents competition it is shown that the one that expands less states is the execution of the program with the Min Max Cutt of algorithm which is correct due to its heuristic that restricts and makes it possible to avoid visiting certain states while the worst result gives the min Max due to its excessive expansion of the game tree.

* Due to its poor performance in terms of time and number of expanded states we could think that the min Max algorithm is not efficient for use in the tic tac toe game but this is not a definitive conclusion that it works for all implementation situations while the modifications of the min Max are of great help these can vary greatly according to which heuristic will be used and for which situation it will be implemented. 
* The great expansion of the game tree that the min max algorithm has is fundamental in how fast it manages to perform to choose a position that benefits it according to the results of the table seen previously the expanded states in the 3 x3 board could be said that they are shortening according to the algorithms for example the min max has at most 157891 expanded states while the min max alpha beta has at most 1734 and the min max cutt off has at most 798 states,this shows that the visited states could be shortened to more than half of the min max with the alpha beta while with the alpha beta and the cutt off is almost half, this big difference of visited states is not only shown in the 3 x 3 board but also in the consecutive ones because of this it is necessary to think about the construction of heuristics that shorten the visited of unnecessary states to have a faster performance in this games.





## BIBLIOGRAPHY
* Class slides
* https://www.geeksforgeeks.org/minimax-algorithm-in-game-theory-set-5-zobrist-hashing/
* https://github.com/SliMM
* https://github.com/lukejriddle


