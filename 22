import matplotlib
import numpy as np
import matplotlib.pyplot as plt
matplotlib.use('TkAgg')  # Specify a backend, e.g., TkAgg
from mpl_toolkits.mplot3d import Axes3D
from mpl_toolkits.mplot3d.art3d import Poly3DCollection

# Function to generate tesseract vertices
def generate_tesseract():
    vertices = np.array([[-1, -1, -1, -1],
                         [-1, -1, -1, 1],
                         [-1, -1, 1, -1],
                         [-1, -1, 1, 1],
                         [-1, 1, -1, -1],
                         [-1, 1, -1, 1],
                         [-1, 1, 1, -1],
                         [-1, 1, 1, 1],
                         [1, -1, -1, -1],
                         [1, -1, -1, 1],
                         [1, -1, 1, -1],
                         [1, -1, 1, 1],
                         [1, 1, -1, -1],
                         [1, 1, -1, 1],
                         [1, 1, 1, -1],
                         [1, 1, 1, 1]])
    return vertices

# Function to plot tesseract
def plot_tesseract(vertices, rotation_angle):
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')

    # Projecting vertices from 4D to 3D
    projection_matrix = np.array([[1, 0, 0, 0],
                                  [0, 1, 0, 0],
                                  [0, 0, 1, 0]])
    projected_vertices = np.dot(vertices, projection_matrix.T)

    # Define tesseract edges
    edges = [[0, 1, 3, 2, 0],
             [4, 5, 7, 6, 4],
             [0, 4], [1, 5], [2, 6], [3, 7]]

    # Plot tesseract edges
    for edge in edges:
        ax.plot3D(projected_vertices[edge, 0], projected_vertices[edge, 1], projected_vertices[edge, 2], 'k')

    # Set plot limits
    ax.set_xlim([-3, 3])
    ax.set_ylim([-3, 3])
    ax.set_zlim([-3, 3])

    # Rotate tesseract
    ax.view_init(azim=rotation_angle, elev=rotation_angle / 2)

    plt.show()

# Generate tesseract vertices
tesseract_vertices = generate_tesseract()

# Animate tesseract rotation
for angle in range(0, 360, 10):
    plot_tesseract(tesseract_vertices, angle)
