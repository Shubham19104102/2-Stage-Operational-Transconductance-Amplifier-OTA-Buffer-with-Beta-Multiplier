# Two-Stage CMOS OTA Buffer with Beta-Multiplier Biasing

## 📌 Overview

This project presents the design and simulation of a **two-stage CMOS Operational Transconductance Amplifier (OTA)** configured as a **unity-gain buffer**. The design incorporates a **Beta-Multiplier biasing circuit** for generating a stable bias current and uses frequency-compensation techniques to achieve a good balance between gain, stability, bandwidth, slew rate, and settling performance.

The complete design is evaluated through **DC operating-point analysis, AC/loop-gain analysis, transient performance, and PVT (Process, Voltage, and Temperature) simulations**.

---

## 🎯 Objectives

The main objectives of this project are:

- Design a high-gain **two-stage CMOS OTA**.
- Implement a **Beta-Multiplier reference circuit** for bias-current generation.
- Configure the OTA as a **unity-gain voltage buffer**.
- Improve frequency stability using **Miller/frequency compensation**.
- Analyze **open-loop gain and phase margin**.
- Evaluate transient performance including **slew rate and settling time**.
- Perform **PVT analysis** to verify circuit robustness.
- Optimize transistor sizing and bias currents for improved performance.

---

## 🏗️ Circuit Architecture

The design consists of the following major blocks:

### 1. Two-Stage OTA

The OTA uses a two-stage architecture:

**Stage 1 – Differential Gain Stage**

The input differential pair converts the differential input voltage into a current and provides the first stage of voltage gain. Active loads and current-mirror structures are used to obtain high differential gain and efficient current utilization.

**Stage 2 – Gain Stage**

The second stage provides additional voltage gain and drives the output node. Appropriate transistor sizing is used to obtain sufficient output swing and drive capability.

### 2. Beta-Multiplier Bias Circuit

A **Beta-Multiplier reference** is used to generate the required bias current for the OTA.

The circuit establishes a self-biased operating point using the relationship between transistor sizing and current. This provides a convenient bias-current reference for the amplifier and helps maintain consistent operation under different operating conditions.

### 3. Frequency Compensation

A compensation network is incorporated between the internal high-impedance node and the output stage to control the amplifier's dominant pole.

The compensation improves closed-loop stability and helps achieve a suitable **phase margin** when the OTA is operated as a voltage buffer.

### 4. Unity-Gain Buffer

The OTA is connected in a **unity-feedback configuration**, making the circuit operate as a voltage buffer.

Ideally:

$$
V_{out} \approx V_{in}
$$

This configuration allows the OTA to be evaluated for:

- Closed-loop stability
- Settling behavior
- Slew rate
- Bandwidth
- Phase margin
- Output response

---

## 🔬 Simulation Analysis

The design is verified using multiple simulation analyses.

### AC / Loop-Gain Analysis

Loop-gain simulations are performed to determine:

- DC loop gain
- Unity-gain frequency
- Phase margin
- Frequency response
- Stability of the feedback configuration

The loop-gain plots demonstrate the frequency-dependent gain and phase response of the designed amplifier.

---

## 📊 PVT Analysis

To verify the robustness of the design, simulations are performed across different **Process, Voltage, and Temperature (PVT)** conditions.

The following performance parameters are monitored:

| Parameter | Minimum | Maximum | Mean | Specification |
|----------|---------:|---------:|---------:|---------------:|
| Open-Loop Gain | 67.28 dB | 75.37 dB | 71.81 dB | > 70 dB |
| Phase Margin | 58.33° | 83.59° | 73.45° | > 60° |
| Settling Time | 56.23 ns | 214.5 ns | 113.5 ns | < 1 µs |
| Slew Rate | 4.777 V/µs | 18.04 V/µs | 9.982 V/µs | > 4 V/µs |
| Bandwidth | 1.628 kHz | 18.83 kHz | 6.445 kHz | — |
| GBW | 9.08 MHz | 43.52 MHz | 22.62 MHz | — |

The results show that the major performance specifications are satisfied across the simulated PVT conditions, with gain and phase margin remaining close to or above their respective targets.

---

## 📈 Key Performance Results

The design achieves approximately:

- **Open-loop Gain:** 71.8 dB average
- **Phase Margin:** 73.5° average
- **Slew Rate:** 9.98 V/µs average
- **Settling Time:** 113.5 ns average
- **Gain-Bandwidth Product:** 22.6 MHz average

These results indicate a good compromise between **high gain, feedback stability, transient response, and frequency performance**.

---

## 🛠️ Design Considerations

Several design parameters were considered during optimization:

### Transistor Sizing

The width-to-length ratios of MOS transistors were adjusted to control:

- Transconductance ($g_m$)
- Output resistance ($r_o$)
- Current levels
- Voltage headroom
- Gain
- Slew rate

### Bias Current

The bias network determines the operating current of the OTA. Increasing bias current can improve transconductance and slew rate but also increases power consumption.

### Compensation

The compensation capacitor and associated resistance/network influence:

- Dominant pole location
- Unity-gain frequency
- Phase margin
- Settling time
- Stability

Therefore, compensation is optimized to obtain sufficient phase margin without excessively sacrificing bandwidth.

---
Tools & Technologies
CMOS Analog Circuit Design
Operational Transconductance Amplifier (OTA)
Beta-Multiplier Biasing
Miller/Frequency Compensation
AC Analysis
Transient Analysis
PVT Analysis
Loop-Gain Stability Analysis
SPICE-based Circuit Simulation
Xschem

📌 Conclusion

A two-stage CMOS OTA configured as a unity-gain buffer was designed and simulated with a Beta-Multiplier biasing circuit and frequency compensation.

The final design demonstrates approximately 71.8 dB gain, 73.5° phase margin, 9.98 V/µs slew rate, 113.5 ns settling time, and 22.6 MHz GBW on average across the evaluated conditions.

The project demonstrates the complete analog IC design flow from bias generation and transistor-level schematic design to stability analysis, transient verification, and PVT characterization.
