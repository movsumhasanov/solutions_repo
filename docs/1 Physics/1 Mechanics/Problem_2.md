# Problem 2



1. General Equations of Motion in Two Dimensions**  
Using kinematic equations for motion under constant acceleration:  

\[
x = x_0 + v_{0x} t
\]
\[
y = y_0 + v_{0y} t - \frac{1}{2} g t^2
\]

where:  
- \( x_0, y_0 \) = Initial position (often taken as 0)  
- \( v_{0x} = v_0 \cos\theta \) (horizontal velocity)  
- \( v_{0y} = v_0 \sin\theta \) (initial vertical velocity)  

2. Velocity Components at Any Time \( t \)**  
\[
v_x = v_0 \cos\theta
\]
\[
v_y = v_0 \sin\theta - g t
\]

3. Velocity Magnitude and Direction**  
- **Resultant velocity at time \( t \):**  
  \[
  v = \sqrt{v_x^2 + v_y^2}
  \]
- **Direction (angle \( \alpha \) with horizontal):**  
  \[
  \tan\alpha = \frac{v_y}{v_x}
  \]

4. Equation of Trajectory**  
To express \( y \) as a function of \( x \), eliminate \( t \):  
\[
y = x \tan\theta - \frac{g x^2}{2 v_0^2 \cos^2\theta}
\]
This represents the **parabolic** path of the projectile.

5. Time to Reach Maximum Height**  
Since the vertical velocity becomes zero at the peak:  
\[
t_{\text{max}} = \frac{v_0 \sin\theta}{g}
\]

6. Alternative Form for Maximum Height**  
Using the kinematic equation \( v^2 = v_0^2 + 2a s \):  
\[
H = \frac{(v_0 \sin\theta)^2}{2g}
\]

7. Alternative Form for Range**  
Since \( R = v_x \times T \), using \( T = \frac{2 v_0 \sin\theta}{g} \), we get:  
\[
R = \frac{v_0^2 \sin 2\theta}{g}
\]


import numpy as np
import matplotlib.pyplot as plt

g = 9.81  # Acceleration due to gravity (m/s^2)

v0 = float(input("Enter initial velocity (m/s): "))
theta = float(input("Enter launch angle (degrees): "))

theta_rad = np.radians(theta)

T = (2 * v0 * np.sin(theta_rad)) / g  # Total time of flight
H = (v0**2 * np.sin(theta_rad)**2) / (2 * g)  # Maximum height
R = (v0**2 * np.sin(2 * theta_rad)) / g  # Horizontal range

t = np.linspace(0, T, num=100)

x = v0 * np.cos(theta_rad) * t  # Horizontal position
y = v0 * np.sin(theta_rad) * t - 0.5 * g * t**2  # Vertical position

plt.figure(figsize=(10, 5))
plt.plot(x, y, label="Projectile Path", color="blue")
plt.axhline(0, color="black", linewidth=0.5)  # Ground line
plt.xlabel("Horizontal Distance (m)")
plt.ylabel("Vertical Distance (m)")
plt.title("Projectile Motion Trajectory")
plt.legend()
plt.grid()

# Show key points
plt.scatter([R], [0], color="red", label="Range (R)")
plt.scatter([R/2], [H], color="green", label="Max Height (H)")
plt.legend()

plt.show()

# Print key results
print(f"Time of Flight: {T:.2f} s")
print(f"Maximum Height: {H:.2f} m")
print(f"Range: {R:.2f} m")


