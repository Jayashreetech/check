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

### Banker’s Algorithm
The **Banker’s Algorithm** is a deadlock avoidance algorithm that applies to systems with multiple instances of each resource type. Each process must declare its **maximum resource requirements** in advance. Resource requests are granted only if the system remains in a **safe state** after allocation. 

The Banker’s Algorithm consists of two parts:
- **Safety Algorithm**
- **Resource‑Request Algorithm** 

Limitations:
- Low device utilization.
- Reduced system throughput.

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



