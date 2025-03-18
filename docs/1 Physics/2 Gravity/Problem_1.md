# Problem 1

2. Implications for Astronomy
Determining Planetary Distances: Kepler’s Third Law can be used to calculate the orbital radius (distance from the central body) if the orbital period is known. For example, knowing the orbital period of a satellite or planet and the mass of the central body, we can calculate the radius of the orbit.

Determining Planetary Masses: If the orbital radius and period of a satellite or moon are known, we can rearrange the equation to solve for the mass 
𝑀
M of the central body. This is particularly useful for calculating the mass of planets or stars.

Application to Solar System: For Earth orbiting the Sun, the orbital period is 1 year and the orbital radius is approximately 1 AU (astronomical unit). Using Kepler’s Third Law, we can calculate the period and radius for other planets in the solar system.

3. Practical Applications
Satellite Orbits: By applying Kepler's Third Law, one can determine the altitude at which a satellite must orbit in order to achieve a specific orbital period. This is important in the design and placement of satellites for communication, Earth observation, and GPS systems.

Moon’s Orbit: The relationship can also be applied to the Moon's orbit around Earth, allowing us to calculate the Moon's orbital radius based on its period (approximately 27.3 days).

4. Python Simulation
Python Code for Orbital Period Simulation
Now, let’s write Python code to simulate circular orbits and verify the relationship between the orbital period 
𝑇
T and the orbital radius 
𝑟
r.

Create a file named orbital_simulation.py in Visual Studio Code and use the following code:

python
Copy
Edit
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # Gravitational constant in m^3 kg^-1 s^-2
M = 5.972e24     # Mass of Earth in kg

# Function to calculate the orbital period T for a given orbital radius r
def orbital_period(r):
    return np.sqrt((4 * np.pi**2 * r**3) / (G * M))

# Range of orbital radii (in meters)
radii = np.logspace(6, 8, num=100)  # from 10^6 m to 10^8 m
periods = orbital_period(radii)

# Plotting the relationship between T^2 and r^3
plt.figure(figsize=(8, 6))
plt.plot(radii**3, periods**2, label="T^2 vs r^3")
plt.xlabel('r^3 (m^3)')
plt.ylabel('T^2 (s^2)')
plt.title("Kepler's Third Law: T^2 vs r^3")
plt.grid(True)
plt.legend()
plt.show()
This Python code does the following:

Defines the constants for gravitational force and Earth's mass.
Creates a function to calculate the orbital period 
𝑇
T based on the orbital radius 
𝑟
r.
Generates a range of orbital radii and calculates the corresponding orbital periods.
Plots the relationship between 
𝑇
2
T 
2
  and 
𝑟
3
r 
3
 .
Running the Simulation
To run the simulation:

Save the code as orbital_simulation.py.
Open a terminal in Visual Studio Code and run the script:
bash
Copy
Edit
python orbital_simulation.py
The graph will appear showing the linear relationship between 
𝑇
2
T 
2
  and 
𝑟
3
r 
3
 , verifying Kepler's Third Law.
5. Discussion
Orbital Period vs Radius: As shown in the simulation and the theoretical derivation, the square of the orbital period 
𝑇
2
T 
2
  is directly proportional to the cube of the orbital radius 
𝑟
3
r 
3
 . This relationship holds for circular orbits, but for elliptical orbits, the same basic form of the law applies, though it involves the semi-major axis rather than the radius.

Real-World Examples: This law is crucial for understanding the orbits of the planets in the solar system. For example, knowing the orbital period of a planet allows astronomers to determine its distance from the Sun and vice versa. Similarly, the Moon's orbit around Earth follows the same relationship.

6. Conclusion
Kepler’s Third Law provides a simple but powerful tool for understanding the motion of celestial bodies. By analyzing the relationship between the square of the orbital period and the cube of the orbital radius, we gain insight into the dynamics of orbital systems, from planets to satellites. The derived equation 
𝑇
2
∝
𝑟
3
T 
2
 ∝r 
3
  forms the foundation for further studies in celestial mechanics, and its implications extend beyond simple planetary motion to applications in satellite technology, space exploration, and gravitational research.

Notes for Writing the Report in Visual Studio Code:
Use Markdown format (.md) for the report sections.
For Python code, create a separate Python script (.py).
Run the code in an integrated terminal or any Python environment.
The Markdown document will support rich formatting, so you can also include images or figures if necessary.
This structure will allow you to document your theoretical work, calculations, and code in a well-organized and easy-to-read format in Visual Studio Code!