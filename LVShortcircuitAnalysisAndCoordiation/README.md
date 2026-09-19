# LV Power Distribution & Protection Coordination (IEC 60909)

**Project:** Al-Nour Developments Commercial Building (8-Story)  
**Role:** Lead Electrical Consultant  
**Author:** Basil Mudathir Ali Ali  

## 1. Project Overview

This repository contains the complete Detailed Engineering Design (DED) for the low-voltage (LV) electrical distribution network of an 8-story commercial facility located in Khartoum. Due to local grid volatility and transient events, the primary engineering objective was to design a highly resilient, fault-tolerant protection scheme that guarantees **total vertical selectivity (discrimination)** while strictly adhering to IEC standards.

## 2. Engineering Methodology

The design utilizes a **Software-First with Manual Benchmark Verification** approach:

* **Primary Simulation Engine:** Schneider Electric Ecodial.
* **Manual Verification:** Rigorous mathematical benchmarking of the worst-case critical path using symmetrical components and IEC 60909 equivalent voltage source methods.
* **Documentation:** LaTeX for high-fidelity technical and mathematical reporting.

## 3. Key Technical Parameters

* **System Topology:** 400/230V, 3-Phase, 4-Wire.
* **Earthing Configuration:** Strict TN-S.
* **Utility Source (MDB Incoming):**
  * 3-Phase Prospective Fault ($I_{k3}$): 20 kA
  * 1-Phase Earth Fault ($I_{k1}$): 15 kA
* **Load Profile:** 150 kVA continuous lumped load per Sub-Main Distribution Board (SMDB).

## 4. Repository Structure

This repository serves as a transparent engineering audit trail. It includes native source files and compiled deliverables:

* `Ecodial_Model/`: Contains the native `.sch` / `.ecodial` project files detailing the Single-Line Diagram (SLD), cable parameters, and protective device configurations.
* `LaTeX_Source/`: Contains the native `.tex` files and associated assets used to generate the mathematical verification report.
* `Deliverables/`:
  * `Design_Verification_Report.pdf`: Comprehensive manual benchmarking of short-circuit parameters ($I_{k3}''$, $I_{k1}''$) against the simulation engine.
  * `Breaker_Schedule.xls`: Detailed schedule verifying Ultimate Breaking Capacity ($I_{cu}$) and Service Breaking Capacity ($I_{cs}$) compliance.
  * `TCC_Plots.pdf`: Time-Current Characteristic curves demonstrating 100-200ms grading margins and zero overlap between cascading tiers.

## 5. Key Engineering Highlights

* **Fault Attenuation & Sizing:** Tracked cable impedance ($R$, $X$) across a 90-meter vertical riser to calculate exact fault attenuation, allowing for optimized, cost-effective downstream switchgear specification without compromising safety.
* **Total Selectivity:** Implemented a cascading 3-tier architecture (ACB $\rightarrow$ MCCB $\rightarrow$ MCB) using a combination of chronometric (time-delayed ETUs) and energy-based (current-limiting) discrimination techniques.
* **Shock Protection Guarantee:** Mathematically validated that the minimum earth fault current at the absolute end of the circuit ($646 \text{ A}$) securely exceeds the magnetic trip threshold ($10 \times I_n$) of the specified Type C MCBs, guaranteeing instantaneous clearance and IEC 60364-4-41 compliance.