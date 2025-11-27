# 📚 Adaptive Filtering in Biomedical Signal Processing (AF-BSP)
The lecture focuses entirely on Adaptive Filtering and its critical role in processing non-stationary biomedical signals (AF-BSP).
This content, both the theoretical slides and practical code examples, is intended to support students and researchers in understanding and applying adaptive filtering techniques for analyzing biomedical data.

## 💡 Key Topics
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
