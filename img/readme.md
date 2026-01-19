<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:1e3c72,100:2a5298&height=120&section=header&text=Deadlock%20Mini%20Project&fontSize=38&fontColor=ffffff" />
</p>


# Deadlock Avoidance and Detection Algorithms – Operating Systems Mini Project

## Project Objective
- Develop a code of **deadlocks**, which prevent sets of concurrent processes from completing their tasks.
- Present a number of different methods for **preventing or avoiding deadlocks** in a computer system.

---

## Deadlock
A process requests resources; if the resources are not available at that time, the process enters a waiting state. Sometimes, a waiting process is never again able to change state, because the resources it has requested are held by other waiting processes. This situation is called a **deadlock**.

A deadlock can occur **if and only if** all four conditions hold simultaneously:

1. **Mutual Exclusion:** At least one resource cannot be shared.
2. **Hold & Wait:** Processes hold resources while requesting additional ones.
3. **No Preemption:** Resources cannot be forcibly taken from a process.
4. **Circular Wait:** There is a cycle of processes where each waits for a resource held by the next.

---

## Visual Models for Deadlocks

### Resource Allocation Graph (RAG)
<div align="right">
<img src="images/resource_allocation_graph.png" alt="Resource Allocation Graph" width="300">
</div>
A **Resource Allocation Graph** represents processes and resources as nodes and the allocation/request relationships as edges.
- A **cycle** in the **Resource Allocation Graph (RAG)** (with single-instance resources) indicates a deadlock.
- If no cycle exists, the system is free from deadlocks.

---

### Wait‑For Graph
<div align="right">
<img src="images/wait_for_graph.png" alt="Wait‑For Graph" width="260">
</div>
The **Wait‑For Graph** simplifies the **RAG** by removing resource nodes; edges show which process is waiting for another.
A **cycle in the Wait‑For Graph** implies a deadlock among processes.

---

## Methods for Handling Deadlocks

### Deadlock Prevention
Deadlock prevention ensures at least one of the necessary conditions does not hold:
- Disallow **hold & wait** by requesting all resources at once.
- Enable **preemption** where resources can be forcibly reallocated.
- Impose **resource ordering** to prevent **circular wait**.

---

### Deadlock Avoidance
Deadlock avoidance ensures the system **never enters an unsafe state**.

**Single instance of a resource type**
- Use a **Resource Allocation Graph**.

Graph-based avoidance:
- Analyze the **Resource Allocation Graph (RAG)** before allocation to prevent cycles that could lead to deadlock.

**Multiple instances of a resource type**
- Use the **Banker’s Algorithm**.

---

### Banker’s Algorithm

The **Resource Allocation Graph (RAG) algorithm** is not applicable to resource allocation systems with multiple instances of each resource type.
The deadlock avoidance algorithm is applicable to such systems but is less efficient than the RAG scheme.
This algorithm is commonly known as the **Banker’s Algorithm**.

- Assumes processes declare their maximum resource needs in advance.
- Checks each resource request to ensure the system remains in a **safe state** after allocation.
- Grants requests only if a **safe sequence** exists, meaning all processes can complete without causing deadlock.
- Dynamically avoids deadlocks by refusing requests that could lead to unsafe states.

**Limitation:**
- Low device utilization
- Reduced system throughput

---

## Safe State

//<img src="https://github.com/jayashree1100/check/blob/main/img/img.png" alt="Safe State Diagram" align="right" width="110" height="110" //style="margin-left:20px; margin-bottom:0; margin-top:0;">
![Safe State Diagram](https://github.com/jayashree1100/check/blob/main/img/img.png){: style="float:right; margin-left:20px;" width="150"}A system is in a **safe state** if it can allocate resources to each process in some order and still avoid a deadlock.
A **safe sequence** ensures all processes can complete without deadlock.

All resource requests are analyzed before allocation to ensure the system remains in a **safe state**. Unsafe states may lead to deadlocks.
This image shows a system in **safe, unsafe, and deadlocked states**, clearly indicating which sequences allow processes to complete safely.

---

## Implementation & Algorithms
- Developed modular **C programs** to simulate deadlock scenarios.
- Implemented and tested the following algorithms:

1. [Safety Algorithm](./Safety%20Algorithm/README.md)
2. [Banker’s Algorithm](./Banker's%20Algorithm/README.md)
3. [Resource Request Algorithm](./Resource%20Request%20Algorithm/README.md)
4. [Deadlock Detection Algorithm](./Deadlock%20Detection/README.md)

- Programs simulate multiple processes and resource request/release sequences.
- Outputs indicate **safe, unsafe, and deadlocked states**, validating theoretical concepts.

---

## Applications
- **Ticket Booking Systems:** Prevents multiple users from waiting indefinitely for seat allocation resources.
- **Printers and Peripheral Devices:** Ensures multiple processes do not block each other when accessing shared printers or scanners.
- **Banking Transactions:** Avoids deadlocks in multi-account transfers where multiple resources (accounts) are accessed concurrently.
- **Manufacturing Automation:** Coordinates robotic arms or machines that require shared tools or parts to prevent process halts.
- **Airport Baggage Handling:** Ensures smooth operation when multiple conveyors and loaders share common resources.
- **Online Gaming Servers:** Manages shared resources like game state or leaderboards to prevent player or server stalls.

---

## Learning Outcomes
- Applied techniques for **avoiding and detecting deadlocks**.
- Distinguished **safe vs unsafe system states** in resource allocation.
- Practiced **process coordination and resource management** in concurrent systems.

---

## Project Nature
Completed as a **semester evaluation mini project** for the **Operating Systems course**, focusing on **practical implementation of deadlock handling mechanisms**.
