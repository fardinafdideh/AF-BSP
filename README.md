# 📚 Adaptive Filtering in Biomedical Signal Processing (AF-BSP)
The lecture focuses entirely on Adaptive Filtering and its critical role in processing non-stationary biomedical signals (AF-BSP).
This content, both the theoretical slides and practical code examples, is intended to support students and researchers in understanding and applying adaptive filtering techniques for analyzing biomedical data.

## 💡 Key Topics 
📂 `Adaptive Filtering in Biomedical Signal Processing.pdf` 
### Foundations & Theory
- What are Adaptive Filters? Dynamic, self-adjusting digital filters that optimize performance in real-time without prior knowledge of signal or noise characteristics.
- Why Biomedical Signals Need Them? To handle non-stationary signals (e.g., ECG, EEG) contaminated by time-varying noise (e.g., muscle tremors, electrical artifacts) that traditional fixed filters cannot effectively manage.
- Core Principles: The filtering and adjustment process is governed by an optimization algorithm using a Cost Function (typically Mean Square Error - MSE) to minimize the Error Signal.
- Key Concepts: Detailed discussion on Convergence (how coefficients reach optimal values) and Steady-state Error (the residual error after convergence).
- Filter Types: Classification into Linear Adaptive Filters (e.g., FIR, IIR, Kalman, Lattice) and Nonlinear Adaptive Filters (e.g., Volterra, Neural Network-Based, Kernel).

### Algorithms and Implementation
- General Adaptive Filter Algorithm: The basic structure involving an Input Signal, an Adaptive Filter, a Desired Signal, and an Adapting Algorithm driven by the Error Signal.
- Key Algorithms: Detailed comparison of major algorithms:
  - LMS (Least Mean Squares): Simple, low complexity, but can be slow to converge.
  - NLMS (Normalized Least Mean Squares): A variant of LMS with improved convergence speed and robustness.
  - RLS (Recursive Least Squares): Faster convergence and smaller steady-state error than LMS, but higher computational complexity.
  - AP (Affine Projection): A generalization of LMS that balances convergence speed and complexity relative to RLS.

### Applications in Biomedical Signal Processing
- Core Applications: System Identification, Inverse System Identification (Equalization), Prediction, and Noise Cancellation.
- ECG Enhancement: Non-invasive fetal ECG extraction and reduction of artifacts like power line interference, muscle artifacts, and baseline wander.
- EEG Enhancement: Reduction of artifacts such as eye blinks, cardiac activity, power line interference, and muscle/head movements to enhance brain wave pattern recognition (e.g., for BCI).
- EMG Enhancement: Removing artifacts like ECG interference and involuntary motion for better signal analysis.
- Blind Adaptation: Strategies for real-world applications where the desired signal is not available, relying only on statistical properties.

## 💻 Interactive Demonstration I: Adaptive Filters in BSP 
📂 `code/adaptive_filters_demonstration.ipynb`

This Jupyter Notebook provides a practical, step-by-step interactive demonstration of adaptive filtering techniques, complementing the theoretical material in the provided PDF lecture slides. 
The focus is on using these algorithms for noise cancellation in biomedical signals where noise characteristics are unknown or time-varying.
A realistic ECG signal with proper PQRST morphology is generated, then deliberately contaminated with common artifacts: powerline interference (60 Hz), baseline wander (low-frequency drift), and white noise (simulating muscle artifacts).
Python classes for three fundamental adaptive filters are implemented and compared: LMS (Least Mean Squares), NLMS (Normalized LMS), and RLS (Recursive Least Squares).
A signal correlated with the noise is generated to simulate a reference signal (a requirement for basic adaptive noise cancellation setup).
The notebook tests each algorithm's ability to clean the noisy ECG signal, measured by the Signal-to-Noise Ratio (SNR) improvement.
RLS provides the most significant SNR improvement, demonstrating its superior tracking of non-stationary noise.
LMS and NLMS offer moderate improvement but are significantly more computationally efficient.
The selection of the appropriate filter depends on the application constraints.

## 💻 Interactive Demonstration II: Power Line Interference (PLI) Cancellation
📂 `code/Power_Line_Interference_Cancellation_of_an_ECG_Signal_using_Adaptive_Filters.ipynb`

This Notebook provides a real-world application of the adaptive filtering principles discussed in the main lecture. 
It focuses on the crucial task of removing Power Line Interference (PLI), a ubiquitous source of noise (typically 50 or 60 Hz) in Electrocardiogram (ECG) recordings.
The notebook demonstrates the Adaptive Noise Cancellation (ANC) architecture, which is highly effective because PLI is often highly correlated with a reference signal (simulated in the notebook), allowing the adaptive filter to track and remove only the interference.

## 💻 Interactive Demonstration III: Kalman Filter in Biomedical Estimation
📂 `code/kalman_filter_demonstration.ipynb`

Unlike the simpler LMS-family algorithms, the Kalman Filter is designed to handle state-space models, making it ideal for tracking hidden physiological parameters (states) that are only indirectly observed through noisy measurements.
State-Space Modeling is how to model a dynamic system (like a physiological process) using a set of state variables and transition matrices, which is the foundation for KF. 
The primary application in this notebook is the estimation of a dynamic signal (the 'true' physiological state) corrupted by significant measurement noise. 
This is analogous to tasks like: Tracking Fetal Heart Rate from a noisy abdominal ECG; Estimating Muscle Force (state) from a noisy EMG signal (measurement); and Real-time tracking of heart rate variability (HRV) metrics.
