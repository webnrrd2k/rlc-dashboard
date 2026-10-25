# AC Circuit Vector Matrix Pro-Dashboard

An interactive, cross-platform HTML5 web application designed for electrical trade school students and engineering peers to simulate, solve, and visualize series and parallel AC RLC, RL, and RC circuits in real time.

This project delivers comprehensive step-by-step mathematical telemetry alongside matching phasor vector maps and power triangles to bridge the gap between abstract textbook formulas and spatial vector behavior.

## Features

*   **Dual Network Configurations:** Seamlessly switch between **Series RLC** and **Parallel RLC** networks.
*   **Dynamic RL/RC/LC Handling:** Input `0` for any missing component to evaluate pure RL, RC, or LC configurations without breaking the mathematical engine.
*   **Real-Time Vector Graphics:** 
    *   **Phasor Maps:** Visualizes individual voltage component vectors ($E_R, E_L, E_C$) for series layouts and branch currents ($I_R, I_L, I_C$) for parallel layouts.
    *   **Power Triangles:** Renders True Power (W), Reactive Power (VARs), and Apparent Power (VA) triangles updating instantly with slider adjustments.
*   **Circuit Schematic:** Draws the series or parallel circuit with component values and reactances.
*   **Step-by-Step Solution:** Shows every formula with the numbers substituted in, plus check calculations.
*   **Live Parameter Telemetry:** Automatically calculates and displays total network Impedance ($Z$), Total Current ($I_T$), Power Factor ($PF$), Phase Angle ($\theta$), and Resonant Frequency ($f_0$).
*   **Automated Net-State Flagging:** Instantly displays a color-coded status banner revealing whether the circuit is operating in a **Net Inductive (Lagging)**, **Net Capacitive (Leading)**, or **Resonant (Unity)** state.

---

## How to Run

**Online:** https://webnrrd2k.github.io/rlc-dashboard/ (served by GitHub Pages from `index.html` on the `main` branch).

**Locally:** the app is a single self-contained `index.html` with **zero installations or dependencies**.

1. Download `index.html` (or clone the repo).
2. Double-click it to open it in any modern browser (Chrome, Safari, Firefox, Edge).
3. Works completely offline—no internet connection required.

Set **L** or **C** to `0` to remove that component. In series it is replaced by a wire; in parallel its branch is removed. Type exact values into the number boxes for homework problems—they can go past the slider range.

**Sign convention:** the phase angle θ is reported as a magnitude with *leads/lags*. Internally θ is the impedance angle (positive = inductive, current lags).

---

## 📱 Cross-Platform Compatibility

The dashboard layout is fully responsive and optimized across all major modern desktop and mobile runtime platforms:
*   **Desktop:** Windows, macOS, Linux
*   **Mobile:** Android, iOS (iPhone/iPad)

---

## Covered Electrical Formulas & Logic

The engine underlying the simulation dashboard relies on the following standard trade school parameters:

### Series Configurations
*   **Total Impedance ($Z$):** $\sqrt{R^2 + (X_L - X_C)^2}$
*   **Total Current ($I_T$):** $E_T / Z$ (where $I_T = I_R = I_L = I_C$)
*   **Power Factor ($PF$):** $R / Z$
*   **Phase Angle ($\theta$):** $\tan^{-1}\left(\frac{X_L - X_C}{R}\right)$

### Parallel Configurations
*   **Branch Currents:** $I_R = E_T/R \quad | \quad I_L = E_T/X_L \quad | \quad I_C = E_T/X_C$
*   **Total Current ($I_T$):** $\sqrt{I_R^2 + (I_C - I_L)^2}$
*   **Admittance Matrix ($Y$):** Conductance $G = 1/R$, Susceptance $B = B_C - B_L = (1/X_C) - (1/X_L)$
*   **Power Factor ($PF$):** $I_R / I_T$
*   **Phase Angle ($\theta$):** $\tan^{-1}\left(\frac{I_C - I_L}{I_R}\right)$

### Shared Power Matrix
*   **Apparent Power ($S$):** $E_T \times I_T$ (expressed in VA)
*   **True Power ($P$):** $S \times PF$ (expressed in Watts)
*   **Reactive Power ($Q$):** $S \times \sin(\theta)$ (expressed in VARs)
*   **Resonant Frequency ($f_0$):** $\frac{1}{2\pi\sqrt{LC}}$ (expressed in Hz)

---

## 🤝 Contribution & License

Feel free to clone this project, add features (such as internal inductor coil resistance tracking), or share it with your study groups. Distributed under the MIT License—feel free to use it to ace your exams!
