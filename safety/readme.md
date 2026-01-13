# Safety Algorithm

- The Safety Algorithm determines whether a state is safe if the system can allocate resources to each process in some order and still avoid a deadlock. 
- A system is in a safe state only if there exists a safe sequence.



## Algorithm

1. Let Work and Finish be vectors of length *m* and *n*, respectively.
Initialize:
   - Work = Available
   - Finish[i] = false for i = 0, 1, ..., n − 1

2. Find an index *i* such that:
   - Finish[i] == false
   - Need[i] ≤ Work
   If no such *i* exists, go to step 4.

3. Work = Work + Allocation[i]
   Finish[i] = true
   Go to step 2.

4. If Finish[i] == true for all *i*, then the system is in a safe state.

**Time Complexity:** O(m × n²)



## Data Structures to be Implemented

**Available:** Vector of length *m* indicating the number of available resources of each type.
If Available[j] = k, then k instances of resource type Rj are available.

**Max:** n × m matrix defining the maximum demand of each process.
If Max[i][j] = k, then process Pi may request at most k instances of resource type Rj.

**Allocation:** n × m matrix defining resources currently allocated to each process.
If Allocation[i][j] = k, then process Pi is currently allocated k instances.

**Need:** n × m matrix indicating remaining resource requirement.
Need[i][j] = Max[i][j] − Allocation[i][j]



./safety

