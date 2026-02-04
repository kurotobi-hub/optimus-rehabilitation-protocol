# optimus-rehabilitation-protocol# Optimus Rehabilitation Protocol (ORP)
**Standardizing Human-Robot Interaction for Caregiving & Rehabilitation**

## Overview
This repository defines the "implicit knowledge" of Occupational Therapists (OT) into programmable logic for humanoid robots (e.g., Tesla Optimus). The goal is to move beyond "mechanical assistance" to "regenerative assistance" that empowers the patient's residual capabilities.

## 1. Safety & Stability Logic (The "Safe Zone" Concept)
Most robots prioritize physical stability (ZMP). However, human patients prioritize "psychological stability."
* **Problem:** Patients freeze when the Center of Gravity (COG) moves too close to the edge of the Base of Support (BOS), even if physically safe.
* **Solution: Dynamic Stability Margin (DSM)**
    * Define `Psychological_Limit` = `Physical_Limit` * 0.4 (Initial Setting).
    * Robot must keep COG within this conservative zone initially, expanding it only as the patient builds trust.

## 2. Initiation Protocol (Sensing Intent)
Robots should not wait for voice commands. They must predict movement.
* **Trigger Signal:** **Visual Attention (Gaze)**.
* **Logic:**
    * Voluntary movement is always preceded by visual fixation on the target.
    * `IF` Gaze_Vector aligns with Target_Object `AND` Duration > 0.5s `THEN` Initiate "Assist_Ready_Mode".

## 3. Quality of Movement (OK/NG Signals)
Shortest path is NOT always the best path.
* **NG Signal (Bad Movement):**
    * **High Muscle Activation:** Detected via resistance against the robot arm (Excessive Force).
    * **Breath Holding:** If the patient stops breathing (detected via microphone/chest movement), the robot must interpret this as "High Stress/Rikimi" and reduce speed/load immediately.
* **OK Signal (Good Movement):**
    * Smooth trajectory with continuous breathing rhythm.
    * No unnecessary muscle co-contraction.

## 4. Rejection Signs (HRI Engagement)
* **Disengagement Criteria:**
    * Avoidance of eye contact.
    * Turning body/face away from the robot.
    * Flat or negative voice tone.
* **Action:** If detected, the robot must increase physical distance (Proximity adjustment) and switch to passive observation mode.

## License
MIT License
## 5. UI/UX for Cognitive Decline (Physical Prompting)
When cognitive processing fails, **Physics never fails.**
Instead of verbal commands ("Please stand up"), use **Physiology & Kinematics** to make the movement inevitable.

* **The Principle:** Do not force the patient to move. Adjust the environment (BOS & COG) so that the movement becomes the only natural physical response.
* **Algorithm (Sit-to-Stand):**
    1.  **BOS Optimization:** Robot ensures patient's feet are grounded and stable.
    2.  **COG Shift:** Robot guides the upper body forward.
    3.  **Inevitable Reaction:** Once COG passes the critical point of the BOS, the patient's **Postural Control System** automatically triggers leg extension to prevent falling.
    * *Result:* The patient stands up "reflexively" without needing to understand the verbal instruction.
