Robot Navigation and Calibration Project

Overview

This project focuses on the development of a compact robot equipped with advanced navigation and calibration strategies. The robot employs the A* algorithm for pathfinding and precise control methods for movement and turning.

1. Design Choices

Robot Design

Initial Footprint: The robot's footprint was minimized to improve compactness.

Traction Issue: During testing, traction problems were identified, leading to the addition of an extra wheel. This partially resolved the issue.

Final Design: Front and rear wheels were replaced to fully address the traction issue. Additionally, the camera was removed to optimize the robot’s weight and complexity.

Illustrations

Include a picture of the robot here to showcase the design.

2. Navigation Strategy

The robot’s navigation strategy leverages the A* algorithm, a robust pathfinding technique.

A* Algorithm Details:

Key Features:

Calculates the f-score for each node:

f-score = g-cost (path cost from the start node) + h-cost (estimated distance to the goal).

Efficiently avoids obstacles by comparing positions against predefined coordinates.

Ensures smooth navigation by calculating Euclidean distances between nodes.

Functions:

check_if_obstacle: Verifies if neighboring points are clear.

a_star_search: Implements the core A* logic.

plot_environment: Visualizes the grid, obstacles, and computed path.

Visualization: Example path generation is illustrated using Python's matplotlib library.

3. Calibration Strategy

Wheel Calibration

Wheel Size: Diameter of 2.2 inches (LEGO Wheel Ø56 with Medium Azure Tire).

Calculation: Using the wheel’s diameter, the circumference was derived to convert wheel rotations into travel distance.

Formula:

Proportional Controllers (Kp):

Straight Movement:



K_p \times (\text{Target Distance} - \text{Traveled Distance})
]

Turning:

Utilizes the robot’s IMU for angle measurements.

Implements radians for smoother operation.



K_p \times (\text{Target Rotation} - \text{Traveled Rotation})
]

4. Python Codebase

Visualization Code

The visualization code includes functions to simulate the robot’s environment and its pathfinding capabilities:

Key Functions:

calculate_distance: Computes Euclidean distance.

generate_neighbors: Identifies valid neighboring nodes.

is_goal_reached: Checks proximity to the goal.

a_star_search: Core A* algorithm implementation.

plot_environment: Visualizes the path and obstacles.

Example Usage:

path_result = a_star_search(start_position, goal_position)
plot_environment(path_result, obstacle_positions, start_position, goal_position)

Robot Movement Code

Key Functions:

MoveStraightForDistance: Moves the robot straight for a given distance.

TurnForAngle: Turns the robot to a specified angle using the IMU.

Example Movement:

TurnForAngle(travel_angle)
MoveStraightForDistance(travel_distance)

Notes:

Includes calibration test functions for accurate distance and angle measurements.

How to Run

Install dependencies (if any).

Use the provided Python scripts for:

Path visualization.

Robot navigation and calibration.

Modify start and goal positions as needed in the scripts.

Execute scripts for testing and deployment on the robot.

Contributions

Contributions are welcome. Please follow standard GitHub workflows.

Future Work

Improve obstacle avoidance with dynamic mapping.

Integrate additional sensors for enhanced environmental awareness.

Optimize navigation algorithms for real-time adjustments.

License

This project is licensed under the MIT License.

