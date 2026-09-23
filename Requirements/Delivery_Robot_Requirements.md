# Delivery Robot System Requirements

| Req. ID | Requirement Statement |
| :--- | :--- |
| **R1** | Upon system initialization, the robot shall remain in the IDLE state until a valid delivery request is received. |
| **R2** | Upon receiving a delivery request, the robot shall switch to the NAVIGATING state and begin moving toward the target destination. |
| **R3** | While navigating, if an obstacle is detected, the robot shall halt normal movement and transition to the AVOIDING_OBSTACLE state. |
| **R4** | Once the detected obstacle is cleared, the robot shall automatically resume navigation toward the target location. |
| **R5** | Upon arriving at the assigned destination, the robot shall transition to the DELIVERING state to execute package handover. |
| **R6** | After package delivery is completed, the robot shall switch to the RETURNING state and begin traveling back to the warehouse. |
| **R7** | If the battery level becomes critically low during navigation, the robot shall abort its mission and transition to the RETURNING state. |
| **R8** | Upon reaching the warehouse, the robot shall enter the IDLE state and await the next delivery request. |
| **R9** | The system shall prevent a direct transition from IDLE to DELIVERING without prior navigation to the destination. |
| **R10** | The system shall disallow initiation of the package delivery process while the robot is operating in the AVOIDING_OBSTACLE state. |
