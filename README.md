# Temporal Coincidence Detector using RC Circuits

## Overview
This project explores how biological neurons detect **near-simultaneous signals**, a phenomenon known as **temporal coincidence detection**.  
We recreate this neural mechanism using an **RC-based electronic circuit simulated in LTspice**.

In neural systems, a neuron fires only when multiple incoming signals arrive within a short time window.  
This project models that behavior using **capacitive charge accumulation and comparator threshold detection**.

The system demonstrates how **two time-separated input pulses combine to trigger an output only if they arrive close enough in time**.

---

## Inspiration

The project is inspired by the **Jeffress Model of auditory localization**, which explains how the brain determines the direction of sound by detecting **tiny timing differences between signals arriving at each ear**.

Coincidence detection appears in:

- Auditory processing in the brain  
- Neuromorphic computing systems  
- Signal timing circuits  
- Radar and particle detection systems  

---

## Concept

Each input signal is modeled as a pulse arriving at a dendrite.

- A **single pulse** is too weak to trigger the neuron.
- When **two pulses arrive close together**, their effects combine.
- If the combined voltage crosses a **threshold**, the neuron fires.

This behavior is recreated using an **RC integration circuit and comparator threshold detection**.

---

## Circuit Architecture

The simulation consists of:

- **Two pulse voltage sources** representing neural inputs  
- **Resistors (R1, R2)** that combine signals  
- **RC network (RL + C)** that stores charge temporarily  
- **Comparator with reference voltage (Vref)**  
- **Output node** representing neuron firing  

The capacitor creates a **temporal integration window** allowing signals arriving close in time to accumulate.

---

## Simulation Method

The coincidence detection was simulated in **LTspice** using the following steps:

1. Two `PULSE` sources were used as input signals.
2. Both inputs were fed through resistors into a common node **Vx**.
3. An **RC network** was connected to temporarily store the signal.
4. A **comparator with reference voltage** monitored node **Vx**.
5. A transient simulation (`.tran`) was performed.
6. The delay between pulses was varied using `.step param TD`.
7. The output was analyzed to observe when coincidence detection occurs.

---

## Key Observation

The circuit fires **only when the delay between two pulses is small enough**.

**Large delay**
- First pulse decays before the second arrives  
- Combined voltage never reaches threshold  
- Output remains OFF  

**Small delay**
- Signals overlap and accumulate  
- Threshold voltage is crossed  
- Comparator triggers output  

This creates a **temporal coincidence detection window**.

---

## Tools Used

- **LTspice** – Circuit simulation  
- **RC Circuit Modeling** – Temporal signal integration  
- **Comparator Threshold Detection**

---

## Repository Structure

- **temporal-coincidence-detector/**
  - Phase1_Presentation.pdf
  - Phase2_Presentation.pdf
  - ltspice_circuits/
  - simulation_results/
  - README.md


---

## Applications

- Neuromorphic engineering  
- Brain-inspired computing  
- Sound localization models  
- Signal timing detection circuits  

---

## References

- Jeffress, L. A. (1948). *A Place Theory of Sound Localization*.  
- Concepts in neural coincidence detection and RC temporal integration.


