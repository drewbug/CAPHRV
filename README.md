# Adaptive Flight Training via Pilot Biotelemetry

## FULLY-FUNCTIONAL PROTOTYPE

This is not a "theoretical" project proposal. The code in this repository powers real hardware and controls real flight simulator environments based on live pilot biotelemetry.

### Current System Capabilities:

- Captures real-time heart rate data from commercial smartwatches (Pixel Watch 2)
- Calculates Heart Rate Variability (HRV) in real-time using modern algorithms
- Detects pilot physiological states (stress, cognitive overload, complacency)
- Automatically adjusts flight simulator conditions via Microsoft Flight Simulator plugin
- Creates adaptive training environments that respond to pilot state

---

## System Overview

This project implements a biocybernetic loop for flight training. The system measures a pilot's real-time physiological response via HRV, analyzes their cognitive state, and dynamically adjusts the training environment to optimize learning outcomes.

### System Architecture

```
┌─────────────────────────┐
│  Smartwatch (Worn)      │
│  - PPG Sensor           │ ──▶ Raw heart rate data
│  - CAPHRV App           │ ──▶ HRV calculation
│  - WiFi transmission    │
└─────────────────────────┘
            │
            ▼ (WiFi)
┌─────────────────────────┐
│  Flight Simulator PC    │
│  - MSFS Plugin          │ ──▶ Receives HRV data
│  - Weather Controller   │ ──▶ Modifies conditions
└─────────────────────────┘
```

### Operating Modes

**Stress Inoculation Mode**
- Detects when HRV indicates pilot complacency or under-stimulation
- Automatically introduces challenging conditions (crosswinds, turbulence)
- Maintains optimal training stress by forcing re-engagement

**Adaptive Difficulty Mode**
- Detects when HRV indicates excessive stress or cognitive overload
- Reduces environmental challenges automatically
- Allows trainee to stabilize and build confidence incrementally

---

## Hardware Requirements

Tested and verified hardware:

- **Smartwatch**: Pixel Watch 2 or compatible Wear OS device with PPG sensor
  - WiFi connectivity required

- **Flight Simulator**: PC running Microsoft Flight Simulator
  - MSFS 2020 or later

---

## Software Components

### CAPHRV Android Wear Application
- Runs directly on Wear OS smartwatches
- Extracts raw photoplethysmogram (PPG) sensor data
- Processes signal peaks and calculates inter-beat intervals (IBI)
- Transmits real-time HRV metrics over Wi-Fi

### Microsoft Flight Simulator Plugin
- Exposes API for external control (receives triggers from CAPHRV application)
- Dynamically modifies weather parameters (wind speed, wind direction, turbulence intensity)

---

## Setup Assistance Available

Contact me at andrew.buglione@flwgcap.us for assistance and detailed setup instructions.

This system is ready to deploy for researchers interested in adaptive training technology.

---

## Technical Background

### Heart Rate Variability (HRV)

HRV measures the variation in time intervals between heartbeats. It is a well-established physiological indicator of stress levels, cognitive load, and autonomic nervous system state.

### Training Gap Addressed

This COTS-based system provides objective, real-time physiological measurement to create a data-driven feedback loop for training optimization.

---

## Future Development

### Short-Term
- Consumer-grade electrocardiogram / EKG integration
- Consumer-grade electroencephologram / EEG integration

### Long-Term
- Real-world flight training integration
- Operational mission support (crew monitoring)

---

## Research Citations

This work builds on established research in aviation medicine and biocybernetic systems:

- **Cao et al. (2019).** Heart rate variability and performance of commercial airline pilots during flight simulations. doi:10.3390/ijerph16020237

- **Coste et al. (2025).** A Comparative Study Between ECG- and PPG-Based Heart Rate Sensors for Heart Rate Variability Measurements. doi:10.3390/s25185745

- **Stephens et al. (2018).** Biocybernetic Adaptation Strategies: Machine awareness of human engagement for improved operational performance. doi:10.1007/978-3-319-91470-1_9

- **Zhang et al. (2019).** Motion Artifact Reduction for Wrist-Worn Photoplethysmograph Sensors Based on Different Wavelengths. doi:10.3390/s19030673

- **Shaw & Harrell (2023).** Integrating physiological monitoring systems in military aviation: a brief narrative review of its importance, opportunities, and risks. doi:10.1080/00140139.2023.2194592

---

## Project Information

**Author**: 2d Lt Andrew Buglione
**Organization**: Civil Air Patrol
**Status**: Fully-Working Prototype

---

## Quick Start

Detailed setup instructions available upon request.

1. Install CAPHRV app on compatible Wear OS smartwatch
3. Configure WiFi connection between devices
4. Start the MSFS plugin: `uv run caphrv.py`

---

## Summary

This project is a low-cost "biocybernetic" system that measures a pilot's heartbeats in real-time to optimize training. Using a smartwatch running custom software, the system measures cardiovascular indicators of cognitive focus and feeds the results to its Microsoft Flight Simulator plugin. The simulator then adjusts conditions such as turbulence to keep the pilot in an optimal learning state using biofeedback, avoiding both boredom and overstimulation. I am also exploring other types of heart and brain activity monitors to see how they could be used in real-world flights. These tools could give instructors and crews a clearer picture of how pilots respond under pressure. 

