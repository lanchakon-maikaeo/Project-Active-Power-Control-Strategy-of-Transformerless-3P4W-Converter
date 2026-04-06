# Project-Active-Power-Control-Strategy-of-Transformerless-3P4W-Converter
Article: Active-Power Control Strategy of Transformerless Three-Phase Four-Wire Grid-Connected Converter for Peak Shaving using Battery Energy Storage System(BESS) was simulated by Matlab/Simulink

[![MATLAB/Simulink](https://img.shields.io/badge/MATLAB-Simulink-blue.svg)](https://www.mathworks.com/products/simulink.html)
[![Status: Pre-print](https://img.shields.io/badge/Status-Pre--print-orange.svg)]()

**Disclaimer:** This repository contains the simulation models and pre-print manuscript of an academic paper that is currently pending formal peer review. 
# Overview
<img width="492" height="284" alt="image" src="https://github.com/user-attachments/assets/626c31b0-a315-4f35-82e6-ba5abbec2528" />
(Source: Author)

<img width="881" height="454" alt="image" src="https://github.com/user-attachments/assets/f7722050-df65-4ed8-ac8d-e91ced65310e" />
(Modified from: Marco Landi, "Making vehicle-to-grid a reality: V2G Developments in the UK", 2018).




## 📖 Abstract
This repository presents a novel active-power control strategy for a **Transformerless Three-Phase Four-Wire Grid-Connected Converter**. The system utilizes a Battery Energy Storage System (BESS) to perform **Peak Shaving** in 230/400V low-voltage distribution networks characterized by high densities of Photovoltaic (PV) installations and Electric Vehicle (EV) chargers. 

By eliminating the traditional distribution transformer and employing a **Mid-Point Balancing Circuit**, the proposed topology reduces equipment cost, footprint, and magnetic interference (EMI). The converter is controlled via a cascaded PI controller loop in the $dq0$ reference frame, achieving rapid active power regulation ($\approx 10-50$ ms) while maintaining strict Power Quality standards (IEEE Std. 519).

## ✨ Key Features
* **Transformerless Topology:** Utilizes a 3-phase 4-wire structure with a dedicated Mid-Point Balancing Circuit to stabilize the split-link DC bus capacitor voltage under unbalanced load conditions.
* **Decoupled Control:** Implements Instantaneous Power Theory in the $dq0$ rotating reference frame to independently control Active Power ($P$) and Reactive Power ($Q$).
* **Rapid Response:** Achieves grid-compliant charge/discharge transition times of approximately 10 ms to 50 ms.
* **High Power Quality:** LCL filter design and feed-forward compensation ensure a Total Harmonic Distortion (THD) of less than 5% (with harmonic orders up to the 50th at $< 0.52\%$).
* **Peak Shaving:** Designed to accept real-time active power commands from an Energy Management System (EMS) and smart meters (TLM) to flatten the daily net load profile.

## ⚙️ System Architecture

### 1. Hardware Topology
The system consists of:
* **BESS:** Battery Energy Storage System acting as the power source/sink.
* **Converter:** 3-Phase 4-Wire Converter with an added 4th leg (2 switches + inductor) specifically for Mid-Point Balancing.
* **Filter:** LCL Low-Pass Filter equipped with a passive damping resistor to mitigate resonance frequencies.

<img width="684" height="251" alt="image" src="https://github.com/user-attachments/assets/95ae598f-74a7-4560-9118-fb6ad25676aa" />

### 2. Control Strategy
The software implementation uses a **Cascade Feedback Control** structure:
* **Inner Converter Current Loop:** Designed for fast dynamic response, compensating for cross-coupling EMF and capacitor voltage.
* **Outer Grid Current Loop:** Controls the current at the Point of Common Connection (PCC) directly regulating the active and reactive power exchange with the grid.
* **Mid-Point Balancing Loop:** Operates independently of the output AC control to inject a compensating current into the neutral point, effectively canceling out neutral currents caused by unbalanced loads and minimizing DC-link voltage oscillation.

<img width="931" height="444" alt="image" src="https://github.com/user-attachments/assets/01caa4f5-34a8-47c8-b6a9-e2f8e028cb1e" />

<img width="491" height="138" alt="image" src="https://github.com/user-attachments/assets/c456fb1c-0391-40f3-a7c1-c0de27e5b50c" />

## 📊 Simulation Results (MATLAB/Simulink)
The model was validated using MATLAB/Simulink with a 40 kVA system, 800 V DC bus, and a 10 kHz switching frequency.

* **Active Power Step Response:** The system successfully tracks a 10 kW active power command with a rise time/time constant of $\approx 10$ ms.
* **DC-Link Stability:** The Mid-Point Balancing Circuit effectively reduces low-frequency voltage oscillations at the DC neutral point compared to conventional split-link topologies.
* **Harmonic Compliance:** FFT analysis confirms the grid current conforms to IEEE Std. 519 limits.

<img width="1021" height="485" alt="image" src="https://github.com/user-attachments/assets/445f839b-00d3-4a4f-abaa-c5164f9bdcd6" />
<img width="495" height="259" alt="image" src="https://github.com/user-attachments/assets/2137a6f9-9908-45c3-9478-d713181a5844" />
<img width="498" height="260" alt="image" src="https://github.com/user-attachments/assets/880f6563-62aa-4182-b09c-391adc72c43e" />


## 🚀 Future Work & Contributions
1.  **Active Damping:** Replacing the passive damping resistor in the LCL filter with an active software damping technique to reduce power losses.
2.  **Grid Support Functions:** Expanding the outer control loop to inject reactive power ($Q$) for dynamic voltage regulation (Ancillary Services).
3.  **Ripple Optimization:** Further tuning of the L/C parameters and balancing circuit to minimize high-frequency current ripple.

## 📝 Citation
If you find this model or strategy useful in your research, please consider citing our pre-print:
> Lanchakon Maikaeo. "Active-Power Control Strategy of Transformerless Three-Phase Four-Wire Grid-Connected Converter for Peak Shaving using Battery Energy Storage System(BESS)." *Metropolitan Electricity Authority (MEA), Thailand*, 2026.

## ✉️ Contact
**Lanchakon Maikaeo** Power Usage Inspection Department, Distribution Equipment Division
Metropolitan Electricity Authority (MEA), Thailand  
Email: 
