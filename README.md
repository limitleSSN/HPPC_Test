# 🔋 HPPC Battery Analysis: Golf Cart vs. E-Scooter

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-Pandas_Matplotlib-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## 📌 Project Overview
**Timeline:** May 2025 – July 2025  
**Context:** EV Battery Performance Benchmarking

This repository contains the analysis scripts and data processing logic for **Hybrid Pulse Power Characterization (HPPC)** tests performed on two commercial electric vehicle battery packs. The project evaluates the **Internal Resistance ($R_{in}$)** and **Power Capability** of Li-ion NMC (Golf Cart) vs. LiFePO4 (E-Scooter) chemistries.

### 🎯 Key Objectives
* **Compare Chemistries:** Analyze how NMC and LFP batteries differ in voltage sag and power delivery.
* **Resistance Mapping:** Calculate internal resistance across the State-of-Charge (SoC) range (10% - 100%).
* **Power Capability:** Determine the maximum discharge and charge power limits for BMS calibration.

---

## 📂 Repository Structure

| File Name | Description |
| :--- | :--- |
| **`Golf-cart.py`** | Analysis script for the **48V NMC Golf Cart Battery**. Processes raw pulse data to extract resistance and power curves. |
| **`E-Bike.py`** | Analysis script for the **60V LFP Scooter/E-Bike Battery**. Handles the flatter voltage curve characteristics of LFP chemistry. |
| **`Randomday-testplot`** | A plotting utility to visualize a random day's dataset from the 33-day production consistency study. useful for spot-checking data quality. |
| **`README.md`** | Project documentation (this file). |

---

## 🔋 Battery Specifications

| Feature | **System A: Golf Cart** | **System B: E-Scooter** |
| :--- | :--- | :--- |
| **Chemistry** | **Li-ion NMC** | **LiFePO4 (LFP)** |
| **Nominal Voltage** | 48V | 60V |
| **Capacity** | 100 Ah | 30 Ah |
| **Test Pulse** | 80 A (10s) | 30 A (10s) |
| **Key Finding** | Higher peak power, but higher voltage sag. | Very stable voltage, lower peak power. |

---

## 📊 Results Summary

### 1. Resistance vs. SoC
* **Golf Cart (NMC):** Resistance drops significantly as the battery charges (from **6.5 mΩ** at 10% SoC to **3.8 mΩ** at 100% SoC).
* **Scooter (LFP):** Resistance remains relatively flat (~50 mΩ) across the middle SoC range (20-80%), typical of LFP stability.

### 2. Power Capability
* **Discharge Power:** The Golf Cart pack demonstrated a peak discharge capability of **42 kW**, whereas the smaller Scooter pack peaked at **3.0 kW**.
* **Regen (Charge) Limits:** The data helps define safe regenerative braking limits to prevent plating.

---

## 🚀 How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/HPPC-Battery-Analysis.git](https://github.com/yourusername/HPPC-Battery-Analysis.git)
    ```

2.  **Install dependencies:**
    ```bash
    pip install pandas matplotlib
    ```

3.  **Run the analysis:**
    * To analyze the Golf Cart data:
        ```bash
        python Golf-cart.py
        ```
    * To analyze the E-Scooter data:
        ```bash
        python E-Bike.py
        ```

---

## 📜 License
This project is open-source and available under the MIT License.
