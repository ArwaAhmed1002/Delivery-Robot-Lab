# Delivery Robot State Model

## Task 2: System States
* **IDLE**: The robot is waiting at the warehouse for an incoming delivery request.
* **NAVIGATING**: The robot is actively moving toward the assigned delivery destination.
* **AVOIDING_OBSTACLE**: The robot is executing avoidance maneuvers around a detected hazard.
* **DELIVERING**: The robot is at the destination executing the package handover.
* **RETURNING**: The robot is traveling back to the central warehouse base.

## Task 3: System Events & Conditions
* **Delivery Request Received**: Triggered when a new delivery task is dispatched to the robot.
* **Obstacle Detected**: Triggered when sensors detect a physical path blockade during movement.
* **Obstacle Avoided**: Triggered when the path is verified clear after maneuvering.
* **Destination Reached**: Triggered when proximity sensors confirm arrival at the target location.
* **Delivery Successful**: Triggered when package handover verification is complete.
* **Critical Battery**: Triggered when battery charge drops below the minimum threshold.
* **Warehouse Reached**: Triggered when sensors confirm return to the home warehouse base.
