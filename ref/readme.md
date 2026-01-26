# Deadlock Avoidance and Detection Algorithms – Operating Systems Mini Project

## Project Objective
- Develop a code of **deadlocks**, which prevent sets of concurrent processes from completing their tasks.
- Present a number of different methods for **preventing or avoiding deadlocks** in a computer system.

## Deadlock
A process requests resources; if the resources are not available at that time, the process enters a waiting state. Sometimes, a waiting process is never again able to change state, because the resources it has requested are held by other waiting processes. This situation is called a **deadlock**.

A deadlock can occur **if and only if** all four conditions hold simultaneously:
1. **Mutual Exclusion:** At least one resource cannot be shared.
2. **Hold & Wait:** Processes hold resources while requesting additional ones.
3. **No Preemption:** Resources cannot be forcibly taken from a process.
4. **Circular Wait:** There is a cycle of processes where each waits for a resource held by the next.
These are the four necessary conditions for deadlock.

## Graph-Based Representation of Deadlocks

### Resource Allocation Graph (RAG)
![Resource Allocation Graph](images/resource_allocation_graph.png)

A **Resource Allocation Graph** represents processes and resources as nodes and the allocation/request relationships as edges. Figure: Resource Allocation Graph showing process–resource relationships.
- A **request edge** (`Pi → Rj`) indicates that process Pi has requested an instance of resource Rj.
- An **assignment edge** (`Rj → Pi`) indicates that resource Rj is currently allocated to process Pi.

If no cycle exists in the graph, the system is free from deadlocks. If a cycle exists (for a single instance of each resource type), it indicates a deadlock.

### Wait‑For Graph
![Wait‑For Graph](images/wait_for_graph.png)

The **Wait‑For Graph** simplifies the Resource Allocation Graph by removing resource nodes and showing only the waiting relationships between processes. In a Wait‑For Graph, a directed edge `Pi → Pj` means that *process Pi is waiting for a resource held by process Pj*. A cycle in the Wait‑For Graph implies a deadlock among the processes. :contentReference[oaicite:0]{index=0}
Figure: Wait‑For Graph showing waiting relationships among processes.


## Methods for Handling Deadlocks

### Deadlock Prevention
Deadlock prevention ensures that at least one of the necessary conditions for deadlock does not hold:
- Disallow **hold & wait** by requiring all resources to be requested at once.
- Enable **preemption** where resources can be taken from a process.
- Impose **resource ordering** to prevent circular wait.

### Deadlock Avoidance
Deadlock avoidance ensures that the system **never enters an unsafe state**.
- For systems with a **single instance** of each resource type, use the Resource Allocation Graph method.
- For systems with **multiple instances** of each resource, use the **Banker’s Algorithm**. 

## Banker’s Algorithm
The **Banker’s Algorithm** is a deadlock avoidance algorithm that applies to systems with multiple instances of each resource type. Each process must declare its **maximum resource requirements** in advance. Resource requests are granted only if the system remains in a **safe state** after allocation. :contentReference[oaicite:2]{index=2}

The Banker’s Algorithm consists of two parts:
- **Safety Algorithm**
- **Resource‑Request Algorithm** 

Limitations:
- Low device utilization.
- Reduced system throughput.


## Implementation & Algorithms
- Developed modular **C programs** to simulate deadlock scenarios.
- Focused on **deadlock avoidance using the Banker’s Algorithm**.
- The project is organized into the following folders:
  
Banker's Algorithm/
  Safety Algorithm/
  Resource Request Algorithm/
  Deadlock Detection/

- Programs simulate multiple processes and resource request/release sequences.
- Outputs indicate **safe**, **unsafe**, and **deadlocked** states.

## Key Skills & Learning Outcomes
- Applied operating system theory to simulation.
- Implemented Banker’s Algorithm and its subcomponents.
- Analyzed safe vs unsafe states to avoid deadlocks.
- Reinforced understanding of deadlock conditions and handling.
- Practiced C programming for system simulation.

## Project Nature
This project was completed as a **semester mini project** for the Operating Systems course, focusing on practical implementation of deadlock avoidance and detection algorithms.

## Reference
Silberschatz, Abraham, Peter B. Galvin, and Greg Gagne. *Operating System Concepts*, Ninth edition, John Wiley & Sons, 2012.

## Copyright & Attribution
This project is developed for **educational purposes**. Content and descriptions are referenced from *Operating System Concepts* (Silberschatz, Galvin & Gagne, 9th Edition). All rights to the textbook belong to the original authors and publisher. This repository does not include copyrighted material beyond brief educational explanations.

