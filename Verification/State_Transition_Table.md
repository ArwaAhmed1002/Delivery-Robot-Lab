# State Transition Table & Verification Activity

## Task 4: State Transition Table

| Current State | Input / Event | Guard Condition | Next State | Action / Output |
| :--- | :--- | :--- | :--- | :--- |
| **IDLE** | Delivery Request Received | Valid Request | **NAVIGATING** | Start route navigation |
| **NAVIGATING** | Obstacle Detected | Hazard Present | **AVOIDING_OBSTACLE** | Halt route, start avoidance |
| **NAVIGATING** | Destination Reached | Path Clear | **DELIVERING** | Stop motors, hand over package |
| **NAVIGATING** | Critical Battery | Charge < Threshold | **RETURNING** | Abort delivery, re-route to warehouse |
| **AVOIDING_OBSTACLE** | Obstacle Avoided | Path Clear | **NAVIGATING** | Resume travel to destination |
| **DELIVERING** | Delivery Successful | Handover Done | **RETURNING** | Initiate route back to warehouse |
| **RETURNING** | Warehouse Reached | At Base | **IDLE** | Power down drive system, wait for request |

---

## Task 5: Verification Activity Results

### Check 1 — Invalid Transition (`IDLE` -> `DELIVERING`)
* **Can this happen?** No.
* **Violated Requirement:** **R9** (and **R1/R2**). The system explicitly forbids direct transition from IDLE to DELIVERING without navigating to the destination first.

### Check 2 — Missing Transition (`NAVIGATING` -> `AVOIDING_OBSTACLE` without return)
* **Question:** Can the robot continue its delivery if there is no transition back?
* **Answer:** No. Without the return transition (`AVOIDING_OBSTACLE` -> `NAVIGATING`), the robot remains permanently trapped in the obstacle avoidance state and cannot reach its target destination.

### Check 3 — Obstacle During Delivery (`AVOIDING_OBSTACLE` -> `DELIVERING`)
* **Question:** Can the robot move directly from `AVOIDING_OBSTACLE` to `DELIVERING`?
* **Answer:** No. This directly violates **R10**. The robot must return to the `NAVIGATING` state first to verify arrival before executing package delivery.
