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

# Parameters
Pt = 1000
Gt = Gr = 40
lam = 0.05
sigma = 10
Pmin = 1e-13
pi4 = (4*np.pi)**3

# Radar Range Equation
Rmax = ((Pt * Gt * Gr * lam**2 * sigma) / (pi4 * Pmin))**0.25
print("Maximum Radar Range =", Rmax, "meters")

# ----------- Plot 1: Pr vs Range -----------
R = np.linspace(1e3, 200e3, 500)
Pr_R = (Pt * Gt * Gr * lam**2 * sigma) / (pi4 * R**4)

plt.figure()
plt.plot(R/1000, 10*np.log10(Pr_R))
plt.title("Received Power vs Range")
plt.xlabel("Range (km)")
plt.ylabel("Pr (dB)")
plt.grid()

# ----------- Plot 2: Pr vs Pt -----------
Pt_vals = np.linspace(100, 10000, 500)
Rfix = 50e3
Pr_Pt = (Pt_vals * Gt * Gr * lam**2 * sigma) / (pi4 * Rfix**4)

plt.figure()
plt.plot(Pt_vals, 10*np.log10(Pr_Pt))
plt.title("Received Power vs Transmit Power")
plt.xlabel("Pt (W)")
plt.ylabel("Pr (dB)")
plt.grid()

# ----------- Plot 3: Pr vs Gain -----------
G_vals = np.linspace(5, 60, 500)
Pt_fix = 3000
Pr_G = (Pt_fix * G_vals**2 * lam**2 * sigma) / (pi4 * Rfix**4)

plt.figure()
plt.plot(G_vals, 10*np.log10(Pr_G))
plt.title("Received Power vs Antenna Gain")
plt.xlabel("Gain (linear)")
plt.ylabel("Pr (dB)")
plt.grid()

plt.show()


```

__Output__:
   
<img width="862" height="470" alt="download" src="https://github.com/user-attachments/assets/f0ae15ae-61a8-4aa9-8701-95e1f863f900" />


<img width="875" height="470" alt="download (4)" src="https://github.com/user-attachments/assets/fb8a90ee-4e6a-43dc-bbff-b4ba5a57741f" />


<img width="862" height="470" alt="download (1)" src="https://github.com/user-attachments/assets/a53e0152-e372-49c0-b6f6-35e522db9a5a" />

__Result__:
   
The maximum range of the radar system was successfully calculated using Python. By providing the required radar parameters and executing the radar range function, the program produced the correct maximum detectable range value. Thus, the radar range evaluation using Python was completed and verified.




