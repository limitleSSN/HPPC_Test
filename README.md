# 🔋 HPPC Battery Analysis Project

### 📌 What is this project?
This project analyzes the performance of two different electric vehicle batteries using the **Hybrid Pulse Power Characterization (HPPC)** test. 

I performed the test on a commercial battery test machine, exported the raw data, and used **Python** to visualize and compare how these batteries behave under stress.

---

### ❓ What is an HPPC Test?
**HPPC (Hybrid Pulse Power Characterization)** is a standard test used to measure a battery's power capability.

Think of it like a stress test for a battery:
1. We discharge the battery to a specific level (like 80% or 50% charge).
2. We hit it with a **sudden burst of current** (a discharge pulse) for 10 seconds.
3. We let it rest.
4. We hit it with a **charging burst** (a regeneration pulse).

**Why do we do this?**
It helps us calculate the **Internal Resistance**. A good battery has low resistance and doesn't lose much voltage when you accelerate hard.

---

### 🔋 Battery Ratings Used

I tested two different battery packs commonly used in EVs:

| Spec | **Battery A (E-Golf Cart)** | **Battery B (2-Wheeler/Scooter)** |
| :--- | :--- | :--- |
| **Chemistry** | Li-ion NMC | LiFePO4 (LFP) |
| **Voltage** | 48V | 60V |
| **Capacity** | 100 Ah | 30 Ah |
| **Pulse Current** | 80 Amps | 30 Amps |
| **Readings Taken** | 20 Data Points | 33 Data Points |

---

### ⚙️ How the Data Was Collected

1. **The Machine:** I used a programmable Battery Cycle Tester (cycler).
2. **The Process:** I programmed the machine to run the HPPC profile automatically. It monitored Voltage, Current, and Temperature every second.
3. **The Export:** After the test finished, the machine software exported the logs as **.CSV (Excel)** files.

**Raw Data Format:**
The machine gave me columns like:
`Timestamp` | `Voltage (V)` | `Current (A)` | `Temperature (C)` | `Step Time`

---

### 🐍 Python Analysis & Plotting

Since the raw data files are large and hard to read manually, I wrote **Python scripts** to process them.

**What the scripts do:**
1. Load the `.csv` files.
2. Filter the specific pulse regions (the 10-second bursts).
3. Plot graphs to compare the **Voltage Sag** (drop) between the Golf Cart and the Scooter battery.

**Files included in this repo:**
* `data/golf_cart.csv` (Contains 20 key readings)
* `data/scooter.csv` (Contains 33 key readings)
* `plot_results.py` (The script to generate the graphs)

---

### 🚀 How to Run
1. Download this repository.
2. Make sure you have Python installed with pandas and matplotlib:
   ```bash
   pip install pandas matplotlib
