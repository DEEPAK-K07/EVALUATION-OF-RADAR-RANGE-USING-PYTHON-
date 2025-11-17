# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


__Algorithm__:

   Start the program.

Import the required Python libraries (Example: math or numpy for calculations).

Define all the radar input parameters, such as:

Transmitted power

Transmitter gain

Receiver gain

Radar frequency

Radar cross-section

Minimum detectable power

Calculate the wavelength from the given radar frequency.

Create a function that implements the radar range calculation using the input parameters.

Call the function with the defined parameter values.

Compute the maximum radar range inside the function.

Display the final calculated maximum range as output.

End the program.


 __Program__:

  ```c
import numpy as np
import matplotlib.pyplot as plt

# Radar parameters
Pt = 1000          # Transmitted power (W)
G = 40             # Antenna gain (linear)
lam = 0.05         # Wavelength (m)
sigma = 10         # RCS (m^2)
pi4 = (4*np.pi)**3 # (4π)^3 term for radar equation


R = np.linspace(1e3, 200e3, 500)   # Range from 1 km to 200 km
Pr_R = (Pt * G**2 * lam**2 * sigma) / (pi4 * R**4)

plt.figure(figsize=(10,5))
plt.plot(R/1000, 10*np.log10(Pr_R))
plt.title("Received Power vs Range")
plt.xlabel("Range (km)")
plt.ylabel("Pr (dB)")
plt.grid(True)


Pt_values = np.linspace(100, 10000, 500)
R_fixed = 50e3  # 50 km fixed range
Pr_Pt = (Pt_values * G**2 * lam**2 * sigma) / (pi4 * R_fixed**4)

plt.figure(figsize=(10,5))
plt.plot(Pt_values, 10*np.log10(Pr_Pt))
plt.title("Received Power vs Transmit Power")
plt.xlabel("Pt (W)")
plt.ylabel("Pr (dB)")
plt.grid(True)


G_values = np.linspace(5, 60, 500)
Pt_fixed = 3000  # 3 kW transmit power
Pr_G = (Pt_fixed * G_values**2 * lam**2 * sigma) / (pi4 * R_fixed**4)

plt.figure(figsize=(10,5))
plt.plot(G_values, 10*np.log10(Pr_G))
plt.title("Received Power vs Antenna Gain")
plt.xlabel("Antenna Gain (linear)")
plt.ylabel("Pr (dB)")
plt.grid(True)


plt.show()

```

__Output__:
   
<img width="862" height="470" alt="download" src="https://github.com/user-attachments/assets/f0ae15ae-61a8-4aa9-8701-95e1f863f900" />


<img width="875" height="470" alt="download (4)" src="https://github.com/user-attachments/assets/fb8a90ee-4e6a-43dc-bbff-b4ba5a57741f" />


<img width="862" height="470" alt="download (1)" src="https://github.com/user-attachments/assets/a53e0152-e372-49c0-b6f6-35e522db9a5a" />

__Result__:
   
The maximum range of the radar system was successfully calculated using Python. By providing the required radar parameters and executing the radar range function, the program produced the correct maximum detectable range value. Thus, the radar range evaluation using Python was completed and verified.




