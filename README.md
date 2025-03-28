# Ideal Sampling

**Name:** Jeswin Shalom S
**Roll Number:** 212223060106

## Aim
To perform ideal sampling (impulse sampling) of a continuous signal and reconstruct the signal using resampling techniques.

## Tools Required
- Google Colab
- Python 3
- NumPy
- Matplotlib
- SciPy

## Program
```python
# Impulse Sampling
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample

# Define parameters
fs = 100  # Sampling frequency
f = 5  # Signal frequency
t = np.arange(0, 1, 1/fs)  # Time vector

# Generate continuous signal
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Perform sampling
signal_sampled = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Reconstruction of signal
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

## Output Waveform
- **Plot of the continuous-time signal.**
  ![image](https://github.com/user-attachments/assets/659577ca-8ab1-4555-b49a-87f50793ae64)

- **Plot of the sampled signal (impulse sampling).**
  ![image](https://github.com/user-attachments/assets/bbba7c52-355f-4b19-adf9-6feaeea7eeaa)

- **Plot of the reconstructed signal using resampling.**
  ![image](https://github.com/user-attachments/assets/190a8340-0218-4fde-91ca-258f0cc19c79)



## Results
The ideal sampling (impulse sampling) of a continuous signal was successfully performed and visualized. The reconstructed signal closely matches the original continuous-time signal, demonstrating effective resampling.

