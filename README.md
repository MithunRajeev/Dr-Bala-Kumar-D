# IDEAL SAMPLING
## MITHUNRAJEEV V
## 212223060159
## AIM
To study and analyze Ideal Sampling (Impulse Sampling), where a continuous-time signal is sampled using an impulse train, and observe its effects in both time and frequency domains. The experiment aims to verify the sampling theorem, analyze spectral characteristics, and understand signal reconstruction.

## TOOLS REQUIRED
Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.

## PROGRAM
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```
## OUTPUT WAVEFORM
![image](https://github.com/user-attachments/assets/c9cfb257-128f-41a0-97a0-37dfe7fc01d2)
![image](https://github.com/user-attachments/assets/61803944-aea7-4ace-a144-10ef81ee5c56)
![image](https://github.com/user-attachments/assets/0c0b62bc-7218-4b75-be68-ea6fabe716d1)

## RESULT
The result of ideal sampling is a discrete-time signal that retains all the information of the original continuous-time signal is obtained and output is verified.
