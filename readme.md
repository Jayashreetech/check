# Deadlock Avoidance and Detection Algorithms – Operating Systems Mini Project (C)

This repository contains C implementations of **deadlock avoidance and detection algorithms**.  It was implemented as a **mini project** for the Operating Systems course and is based on:  **Operating System Concepts** by Silberschatz, Galvin, and Gagne.

## Objectives
- Develop code to demonstrate deadlocks, where sets of concurrent processes may be prevented from completing tasks.
- Present and implement different methods for **preventing, avoiding, and detecting deadlocks**.

## Introduction
A process may request resources; if they are unavailable, the process enters a waiting state.  Sometimes, a waiting process is never able to proceed because the requested resources are held by other waiting processes.  This situation is called a **deadlock**.


## Deadlock Avoidance
Deadlock avoidance algorithms prevent deadlocks by limiting how requests can be made.  

**Limitation:**  
- Low device utilization  
- Reduced system throughput

## Safe State

A system is in a **safe state** if it can allocate resources to each process in some order and still avoid a deadlock.  A safe sequence ensures all processes can complete without deadlock.

<div style="display:flex; align-items:flex-start; gap:20px;">
<div style="flex:1">
A safe state exists if a safe sequence can be found. Unsafe states may lead to deadlocks.  
All resource requests are analyzed before allocation to ensure the system remains in a safe state.
</div>
<div style="flex:1">
<img src="https://github.com/Jayashreetech/check/blob/main/img/img.png" alt="Safe State Diagram" width="300">
</div>
</div>


## Safe State

A system is in a **safe state** if it can allocate resources to each process in some order and still avoid a deadlock.  <img src="https://github.com/Jayashreetech/check/blob/main/img/img.png" alt="Safe State Diagram" align="right" width="150" height="150" style="margin-left:20px; margin-bottom:0; margin-top:0;">
A safe sequence ensures all processes can complete without deadlock.



A safe state exists if a safe sequence can be found. Unsafe states may lead to deadlocks.  
All resource requests are analyzed before allocation to ensure the system remains in a safe state.  
This image shows a system in safe, unsafe, and deadlocked states, clearly indicating which sequences allow processes to complete safely.











## Algorithms Implemented

1. [Safety Algorithm](./Safety%20Algorithm/README.md)  
2. [Banker’s Algorithm](./Banker's%20Algorithm/README.md)  
3. [Resource Request Algorithm](./Resource%20Request%20Algorithm/README.md)  
4. [Deadlock Detection Algorithm](./Deadlock%20Detection/README.md)

## Repository Structure

