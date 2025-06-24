# Linear Algebra

A Python library providing common geometric and linear algebra functions built on NumPy for 3D transformations, vector operations, and computational geometry.

## Overview

This library contains practical linear algebra functions for 3D graphics, robotics, and computational geometry applications. It includes rotation matrices, vector operations, geometric transformations, and utility functions for working with points, lines, and planes in 3D space.

## Features

- **3D Rotation Matrices**: X, Y, Z axis rotations and general rotation combinations
- **Vector Operations**: Magnitude, unit vectors, angles between vectors, scaling
- **Rodrigues Rotation**: Rotation around arbitrary axes using Rodrigues' formula
- **Geometric Transformations**: Translation, affine transformations, homogeneous coordinates
- **Line and Plane Operations**: Intersections, projections, distance calculations
- **2D/3D Geometry**: Line-point distances, line-line distances, plane intersections
- **Utility Functions**: Skew matrices, sigmoid functions, numerical comparisons

## Installation

```bash
# Clone the repository
git clone https://github.com/KeerthiSagarSN/linearalgebra.git
cd linearalgebra

# Install dependencies
pip install numpy sympy scipy matplotlib
```

## Dependencies

- Python 3.x
- NumPy
- SymPy
- SciPy
- Math

## Quick Start

```python
import numpy as np
from linearalgebra import *

# Create rotation matrices
rx = R_X(45)  # Rotate 45 degrees around X-axis
ry = R_Y(30)  # Rotate 30 degrees around Y-axis
rz = R_Z(60)  # Rotate 60 degrees around Z-axis

# Combined rotation
r_combined = R_r(45, 30, 60)  # X, Y, Z rotations

# Vector operations
v1 = np.array([1, 2, 3])
v2 = np.array([4, 5, 6])

# Calculate vector magnitude
magnitude = V_mod(v1)

# Get unit vector
unit_v1 = V_unit(v1)

# Calculate angle between vectors
angle = V_ang(v1, v2)

# Rodrigues rotation around arbitrary axis
axis = np.array([[0], [0], [1]])  # Z-axis
rotation_matrix = R_Rod(np.pi/4, axis)  # 45 degrees

# Point transformations
p1 = np.array([[1], [2], [3]])
p2 = np.array([[4], [5], [6]])
translated_point = T_pt(p1, p2)
```

## Main Functions

### Rotation Functions
- `R_X(ang)` - Rotation matrix around X-axis (degrees)
- `R_Y(ang)` - Rotation matrix around Y-axis (degrees)  
- `R_Z(ang)` - Rotation matrix around Z-axis (degrees)
- `R_r(angx, angy, angz)` - Combined rotation matrix
- `R_Rod(theta, v_axis)` - Rodrigues rotation around arbitrary axis
- `R_L(theta, l_p1, l_p2)` - Rotation around arbitrary line

### Vector Functions
- `V_mod(V)` - Vector magnitude/length
- `V_unit(V)` - Unit vector
- `V_ang(V1, V2)` - Angle between vectors
- `V_scale(V, scale)` - Scale vector by factor
- `V_det(V1, V2)` - 2D vector determinant

### Geometric Functions
- `proj_point_plane(p_norm, pt_plane, p1)` - Project point onto plane
- `twolines_intersection(p1, v1_ax, p2, v2_ax)` - Find intersection of two lines
- `dist_line_point_2D(l1, pt)` - Distance from point to line in 2D
- `dist_line_line_3D(e1, e2, r1, r2)` - Distance between two 3D lines
- `plane_plane_intersection(...)` - Intersection of two planes

### Transformation Functions
- `T_pt(inp_mat, disp_mat)` - Translate point
- `Transl(i, j, k, pt)` - Translation using homogeneous coordinates
- `V_affine(...)` - Affine transformation matrix

### Utility Functions
- `skew(u)` - 3D skew-symmetric matrix
- `skew_2D(u)` - 2D skew matrix
- `isclose(a, b)` - Floating point comparison
- `check_ndarray(p_in)` - Array dimension checking

## Usage Examples

### 3D Rotations
```python
# Rotate a point 90 degrees around Z-axis
point = np.array([[1], [0], [0]])
rot_z = R_Z(90)
rotated_point = rot_z @ point
```

### Line Operations
```python
# Find intersection of two lines
p1 = np.array([0, 0, 0])
v1 = np.array([1, 0, 0])  # X direction
p2 = np.array([0, 1, 0])
v2 = np.array([0, 0, 1])  # Z direction

intersection = twolines_intersection(p1, v1, p2, v2)
```

### Distance Calculations
```python
# Distance from point to line in 2D
line = np.array([[0, 0], [1, 1]])
point = np.array([1, 0])
distance = dist_line_point_2D(line, point)
```

## Applications

This library is useful for:
- **3D Graphics**: Object transformations, camera positioning
- **Robotics**: Joint rotations, end-effector positioning  
- **Computer Vision**: Camera calibration, pose estimation
- **Engineering**: Mechanical design, structural analysis
- **Game Development**: 3D object manipulation, physics

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source. Please check with the author for specific license terms.

## Author

**Keerthi Sagar SN**  
GitHub: [@KeerthiSagarSN](https://github.com/KeerthiSagarSN)

---

*A practical linear algebra toolkit for 3D computational geometry*
