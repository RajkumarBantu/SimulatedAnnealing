# 
Simulated Annealing is used to solve the graph partitioning problem, in which we try to divide the nodes of a graph into two disjoint sets of equal size while minimizing the cutset size.
For Simulated Annealing bipartitioning algorithm we follow these steps
Create a random partition and allocate each node to one of the two sets with equal probability.
Determine the cutset between the two cells.
Set the Initial temperature and cooling rate.
Continuously perform these steps until the temperature falls below a specific level.
Create a nearby partition by randomly selecting a node and shifting it to the other set.
Determine the price of the new partition.
Compute the cost difference between the current and new partitions.
Accept the new partition as the current partition if it is less expensive.
Accept the new partition with the expectation that it would be more expensive.
It is determined by the temperature as well as the magnitude of the cost increase.
Using the cooling rate, lower the temperature.
The final partition should be returned.
The acceptance probability of a worse solution is given by the Boltzmann distribution

Approach taken and Data structures used while Simulated Annealing-

Tuple [int, List[int], List[int] simulated annealing(c: int, nets: List[Tuple[int, int]) -> Tuple[int, List[int], List[int].This function takes the number of cells and a list of tuples representing the nets as arguments and returns a tuple containing the cs size and the two partitions that minimize the cs.
The function begins by generating the initial partitions and then calculating the initial cutset size with calculate cs size. The initial temperature and cooling schedule are then set, and the main loop of the simulated annealing algorithm is started.
In each iteration of the loop, the function calls swap cells to generate a new solution and calculates the new cs size using calculate cs size.
The new solution is accepted as the new current solution if it has a lower cs than the current solution. If the new solution is successful 
It is accepted with a probability determined by the current temperature as a larger cs. The cooling schedule is used to update the temperature at the end of each iteration, and the algorithm is repeated until the temperature reaches a very low value. A tuple containing the final cs size and partition lists is returned.
Initially the temperature = 150(was not getting the expected cutsize size and partitions)
After experimentation its 40000
Cooling factor is 0.1
Max iterations is c*1000 where c is number of cells

Simulated Annealing Algorithm used in the program:

Step1	:	Read in netlist file
Step2	:	Split the number of cells and edges
Step3	:	 Set up the initial partitions
Step4	:	 Keep track of best cutset seen so far
Step5	: Set up initial Temperature
Step6	:	 Choose a random pair of cells to swap
Step7	: Calculate the cutset of the swap
Step 8	:	If the cutset is smaller, move to the new partition
Step 9	:	Otherwise, move to the new partition with a probability determined
Step 10 : Decrease the temperature
Step 11 :	Write Output
