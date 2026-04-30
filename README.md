# SKILL LAB PRACTICAL HACKATHON

## Final Project README

> **Project Weight:** 100%  
> **Team Size:** 4 students  
> **Project Duration:** 16 hours  
> **Total Time Available:** 32 effort-hours per team  
> **Project Type:** Playful, interactive, technology-based experience

---

# Before you begin

## Fork and rename this repository

After forking this repository, rename it using the format:

`SKILLLAB_PROR-2026-TeamName`

### Example

`SKILLLAB_PROR-2026-AuroWizards`

Do not keep the default repository name.

---

# How to use this README

This file is your team's **working project document**.

You must keep updating it throughout the build period.  
By the final review, this README should clearly show:

- your idea,
- your planning,
- your design decisions,
- your technical process,
- your build progress,
- your testing,
- your failures and changes,
- your final outcome.

## Rules

- Fill every section.
- Do not delete headings.
- If something does not apply, write `Not applicable` and explain why.
- Add images, screenshots, sketches, links, and videos wherever useful.
- Update task status and weekly logs regularly.
- Use this file as evidence of process, not only as a final report.

---

# 1. Team Identity

## 1.1 Studio / Group Name

`[Your Studio / Group Name Here]`

## 1.2 Team Members

| Name | Primary Role | Secondary Role | Strengths Brought to the Project |
| ---- | ------------ | -------------- | -------------------------------- |
| `Krishnan H` | `[]` | `[]` | `[]` |
| `Dheeraj Moolya` | `[]` | `[]` | `[]` |
| `Nidhi Bamhane` | `[]` | `[]` | `[]` |
| `Rushikesh Sose` | `[]` | `[]` | `[]` |

## 1.3 Project Title

`Adaptive Cruise Control Enabled Robotic Car`

## 1.4 One-Line Pitch

`An ACC-enabled robotic car that intelligently adjusts its movement based on real-time obstacle detection and sensor input.`

## 1.5 Expanded Project Idea

**Response:**  
`The ACC-enabled robo car is a smart robotic system designed to simulate the behavior of adaptive cruise control found in modern autonomous vehicles. The robot uses sensors to detect obstacles in its path and automatically adjusts its movement by slowing down, stopping, or changing direction to maintain a safe distance. This creates an interactive experience where the robot behaves intelligently in a dynamic environment rather than following fixed commands.`

`The system combines Arduino for real-time control of motors and sensors with Raspberry Pi for higher-level processing, communication, and potential extensions like monitoring or advanced logic. IR sensors are used for obstacle detection, a touch sensor provides user control, and a motor driver enables movement. Together, these technologies create a practical demonstration of how real-world autonomous systems work, making the project both educational and engaging by bridging theoretical concepts with hands-on implementation.`

---

# 2. Inspiration

## 2.1 References

List what inspired the project.

| Source Type | Title / Link | What Inspired You |
| ----------- | ------------ | ----------------- |
| `[Video]` | `https://www.instagram.com/reel/DW4CT7WCDry/?igsh=cXg3dzAxYmdncDBo` | `How projection mapping can be used to create interactive digital + physical experiences` |

## 2.2 Original Twist

What makes your project original?

**Response:**  
`This project introduces a simplified Adaptive Cruise Control (ACC) system using low-cost components. Unlike basic obstacle avoidance robots, this system dynamically adjusts speed based on real-time conditions.`

Key unique features:
- Multi-level speed control instead of just stop/go
- LED speed indicator bar (4 levels) for real-time feedback
- IR sensors as safety override for emergency stopping
- Dual-controller architecture (Raspberry Pi + Arduino) for efficient task division

`This combination makes the system more realistic, interactive, and closer to real automotive ACC behavior, while still being achievable within limited time and resources.`

---

# 3. Project Intent

## 3.1 User Journey

Describe exactly how a user will use the project. Make it a story.

**Response:**  
`A user places the robotic car on a track and powers it on. Initially, the system is idle. The user gently taps the touch sensor, which activates the system.`

`The car begins to move forward automatically. As it moves, the system continuously monitors its surroundings.`

`If the path ahead is clear, the car moves at high speed, and all four LEDs glow, indicating maximum speed. As the car approaches an obstacle, the system detects reduced distance and gradually slows down. The LEDs decrease from four to three, then two, showing the reduction in speed.`

`When the car gets very close to an object, the IR sensors detect immediate danger. The system instantly stops the car, and only one LED remains on, indicating a stop condition.`

`If the obstacle is removed, the car automatically resumes motion, increasing speed step-by-step based on available space.`

`At any point, the user can tap the touch sensor again to stop the system completely.`

---

# 4. Definition of Success

## 4.1 Definition of "Usable"

`[Write here]`

## 4.2 Minimum Usable Version

What is the smallest version of this project that still delivers the core experience?

**Response:**  
`[Write here]`

## 4.3 Stretch Features

What features are nice to have but not essential?

`[Write here]`

---

# 5. System Overview

## 5.1 Project Type

Check all that apply.

- [x] Electronics-based
- [x] Mechanical
- [x] Sensor-based
- [ ] App-connected
- [x] Motorized
- [ ] Sound-based
- [x] Light-based
- [ ] Screen/UI-based
- [x] Fabricated structure
- [ ] Game logic based
- [ ] Installation
- [ ] Other:

## 5.2 High-Level System Description

**Response:**  
`The system is a robotic vehicle designed to move intelligently by detecting obstacles and adjusting its motion accordingly. It uses sensors to gather environmental data, processes this data using a central computing unit, and controls motors to perform movement.`

**Input:** The system receives input from sensors:
- **Ultrasonic Sensor:** Measures the distance between the robot and obstacles ahead.
- **Infrared (IR) Sensor:** Detects nearby objects for close-range obstacle detection.

These sensors continuously provide real-time environmental data to the system.

**Processing:**  
The processing is carried out by the Raspberry Pi 4 Model B, which acts as the main brain of the system. It receives sensor data, analyzes distance and obstacle conditions, and based on programmed logic (such as obstacle avoidance or speed control), it decides the movement of the robot.

**Output:**  
The output is the movement of the robot via DC motors connected to the L293D motor driver IC. Based on processing, the robot can move forward, slow down, or stop when an obstacle is detected.

**Physical Structure:**  
The system is built on a mechanical chassis consisting of four wheels connected to DC motors, a mounted Raspberry Pi board, sensors placed at the front for effective detection, and motor driver and wiring integrated into the structure.

## 5.3 Input / Output Map

| System Part | Type | What It Does |
| ----------- | ---- | ------------ |
| `Ultrasonic Sensor (HC-SR04)` | `Input` | `Measures distance to obstacles ahead` |
| `IR Sensors (HW-201)` | `Input` | `Detects close-range obstacles / emergency stop` |
| `Touch Sensor (TTP223)` | `Input` | `Start / Stop system toggle` |
| `Raspberry Pi 4 Model B` | `Processing` | `Main decision-making controller` |
| `Arduino Uno + Motor Driver Shield` | `Processing` | `Motor control and low-level I/O` |
| `DC Gear Motors (x4)` | `Output` | `Drive wheels for movement` |
| `LEDs (x4)` | `Output` | `Visual speed indicator (4 levels)` |

---

# 6. System Design, Sketches and Visual Planning

## 6.1 Concept Architecture/sketch/schematic

Add an early sketch of the full idea.

**Insert image below:**  
`[Upload image and link here]`

## 6.2 Labeled Build Sketch/architecture/flow diagram/algorithm

Add a sketch with labels showing:

- structure,
- electronics placement,
- user touch points,
- moving parts,
- output elements.

**Insert image below:**  
`[Upload image and link here]`

## 6.3 Approximate Dimensions

| Dimension | Value |
| --------- | ----- |
| Length | `16 cm` |
| Width | `16 cm` |
| Height | `8 cm` |
| Estimated weight | `400 g` |

---

# 7. Electronics Planning

## 7.1 Electronics Used

| Component | Quantity | Purpose |
| --------- | --------:| ------- |
| `Raspberry Pi 4 Model B` | `1` | `Main controller (decision making)` |
| `IR Sensors (HW-201)` | `2` | `Obstacle detection` |
| `Ultrasonic Sensor (HC-SR04)` | `1` | `Distance measurement (ACC)` |
| `Arduino Uno (with Motor Driver Shield L293D)` | `1` | `Controls motors` |
| `DC Gear Motors (TT Yellow)` | `4` | `Movement of car` |
| `Touch Sensor (TTP223 Capacitive)` | `1` | `Start/Stop input` |
| `LEDs (Standard 5mm)` | `4` | `Speed indicator` |
| `Battery (Li-ion)` | `2` | `Power supply` |

## 7.2 Wiring Plan

**Response:**  
`The Raspberry Pi is connected to the Arduino Uno via serial/USB communication. The Arduino Uno interfaces with the Motor Driver Shield (L293D) to control four DC gear motors for directional movement. The Raspberry Pi reads input from the Ultrasonic Sensor (HC-SR04) via GPIO pins (Trig and Echo) and from the two IR sensors. The Touch Sensor (TTP223) is connected to a Raspberry Pi GPIO input pin for start/stop control. Four LEDs are connected to Raspberry Pi GPIO output pins through appropriate resistors to indicate speed levels. The battery pack powers the motors via the motor driver at higher voltage, while the Raspberry Pi and Arduino are powered via regulated supply. All components share a common ground.`

## 7.3 Circuit Diagram/architecture diagram

Insert a hand-drawn or software-made circuit diagram.

**Insert image below:**  
`[Upload image and link here]`

## 7.4 Power Plan

| Question | Response |
| -------- | -------- |
| Power source | `Battery (Li-ion pack)` |
| Voltage required | `~6–8.4V for motors (via driver), stepped down to 5V for Raspberry Pi and Arduino` |
| Current concerns | `Motors can draw high current under load, which may cause voltage drops affecting the Raspberry Pi` |
| Safety concerns | `Avoid over-discharging Li-ion batteries, ensure proper voltage regulation, prevent short circuits, and secure wiring to avoid loose connections` |

---

# 8. Software Planning

## 8.1 Software Tools

| Tool / Platform | Purpose |
| --------------- | ------- |
| `Python` | `Decision making based on sensor input (runs on Raspberry Pi)` |
| `Arduino IDE` | `Control motors via motor driver shield` |

## 8.2 Software Logic/Algorithm

**Response:**

- **Startup behavior:**  
  The Raspberry Pi initializes GPIO pins for sensors, LEDs, and touch input. Arduino initializes motor control pins. System enters idle state awaiting touch input.

- **Input handling:**  
  Touch sensor tap is detected on Raspberry Pi GPIO. A single tap activates the system; a second tap stops it.

- **Sensor reading:**  
  Ultrasonic sensor continuously measures distance to obstacles ahead. IR sensors monitor for immediate close-range danger.

- **Decision logic:**  
  Based on measured distance, the system decides speed level:  
  — Far (clear): Full speed, 4 LEDs on  
  — Medium distance: Reduced speed, 3 LEDs on  
  — Close: Slow speed, 2 LEDs on  
  — Very close / IR triggered: Full stop, 1 LED on  
  If obstacle is removed, speed resumes gradually.

- **Output behavior:**  
  Raspberry Pi sends speed/direction commands to Arduino. Arduino drives motors using PWM. LEDs update to reflect current speed level.

- **Communication logic:**  
  Raspberry Pi communicates with Arduino via Serial (USB). Commands include speed level and direction.

- **Reset behavior:**  
  If touch sensor is tapped again, all motors stop and LEDs reset. System re-enters idle state.

## 8.3 Code Flowchart

Insert a flowchart showing your code logic.

Suggested sequence:

- start,
- initialize,
- wait for input,
- read input,
- decision,
- trigger output,
- repeat or reset,
- error handling.

**Insert image below:**  
`[Upload image and link here]`

---

# 9. Bill of Materials

## 9.1 Full BOM

| Component | Quantity | In Kit? | Need to Buy? | Estimated Cost | Material / Spec | Why This Choice? |
| --------- | --------:| ------- | ------------ | --------------:| --------------- | ---------------- |
| `Raspberry Pi 4 Model B` | `1` | `Yes` | `No` | `0` | `4 Model B` | `Main controller for high-level processing` |
| `IR Sensors` | `2` | `Yes` | `No` | `0` | `HW-201` | `Close-range obstacle detection` |
| `Ultrasonic Sensor` | `1` | `Yes` | `No` | `0` | `HC-SR04` | `Distance measurement for ACC` |
| `Arduino Uno (with Motor Driver Shield)` | `1` | `Yes` | `No` | `0` | `L293D` | `Real-time motor control` |
| `DC Gear Motors` | `4` | `Yes` | `No` | `0` | `TT Yellow Gear Motors` | `Continuous rotation for movement` |
| `Motor Driver` | `1` | `Yes` | `No` | `0` | `L293D Shield` | `Bidirectional motor control via PWM` |
| `Touch Sensor` | `1` | `Yes` | `No` | `0` | `TTP223 Capacitive` | `User-friendly start/stop control` |
| `LEDs` | `4` | `Yes` | `No` | `0` | `Standard 5mm` | `Visual speed feedback` |
| `Battery` | `2` | `Yes` | `No` | `0` | `Li-ion` | `Portable power supply` |

## 9.2 Material Justification

**Response:**  
`DC gear motors (TT Yellow) were chosen because the system requires continuous rotation for wheel movement rather than precise angular control. The L293D motor driver shield was selected to allow bidirectional control and speed variation using PWM signals from the Arduino. Raspberry Pi 4 was chosen as the primary controller for its GPIO flexibility and ability to run Python-based sensor logic. Arduino Uno handles low-level motor commands for reliable real-time response. IR sensors supplement the ultrasonic sensor to catch immediate close-range obstacles that the ultrasonic sensor might miss at very short range.`

## 9.3 Items You Chose

| Item | Why Needed | Purchase Link | Latest Safe Date to Procure | Status |
| ---- | ---------- | ------------- | --------------------------- | ------ |
| `BO Motors + Wheels` | `Drive system for car` | `robu.in` | `15th April` | `[Received]` |
| `Buck Converter` | `Stable power for Raspberry Pi` | `local store` | `before testing` | `[Received]` |
| `Li-ion Batteries` | `Portable power` | `local store` | `before testing` | `[Received]` |

## 9.4 Budget Summary

| Budget Item | Estimated Cost |
| ----------- | --------------:|
| Electronics | `400` |
| Mechanical parts | `200` |
| Fabrication materials | `0 (Available on campus)` |
| Purchased extras | `0` |
| Contingency | `300` |
| **Total** | `900` |

## 9.5 Budget Reflection

If your cost is too high, what can be simplified, removed, substituted, or shared?

**Response:**  
`[Write here]`

---

# 10. Planning the Work

## 10.1 Team Working Agreement

**Response:**  
`[Write here — include how tasks are divided, how decisions are made, how progress will be checked, what happens if a task is delayed, and how documentation will be maintained.]`

## 10.2 Task Breakdown

| Task ID | Task | Owner | Estimated Hours | Deadline | Dependency | Status |
| ------- | ---- | ----- | ---------------:| -------- | ---------- | ------ |
| T1 | `Finalize concept` | `All` | `2` | `1st April` | `None` | `Done` |
| `T2` | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |

## 10.3 Responsibility Split

| Area | Main Owner | Support Owner |
| ---- | ---------- | ------------- |
| Concept | `[]` | `[]` |
| Electronics | `[]` | `[]` |
| Coding | `[]` | `[]` |
| Mechanical build | `[]` | `[]` |
| Testing | `[]` | `[]` |
| Documentation | `[]` | `[]` |

---

# 11. Hour Milestones

## 11.1 8-hour Plan (tentatively you may set)

### Bi Hour 1 — Plan and De-risk

Expected outcomes:

- [ ] Idea finalized
- [ ] Core interaction decided
- [ ] Sketches made
- [ ] BOM completed
- [ ] Purchase needs identified
- [ ] Key uncertainty identified
- [ ] Basic feasibility tested

### Bi Hour 2 — Build Subsystems

Expected outcomes:

- [ ] Electronics tests completed
- [ ] CAD / structure planning completed
- [ ] App UI started if needed
- [ ] Mechanical concept tested
- [ ] Main subsystems partially working

### Bi Hour 3 — Integrate

Expected outcomes:

- [ ] Physical body built
- [ ] Electronics integrated
- [ ] Code connected to hardware
- [ ] App connected if required
- [ ] First playable version exists

### Bi Hour 4 — Refine and Finish

Expected outcomes:

- [ ] Technical bugs reduced
- [ ] Playtesting completed
- [ ] Improvements made
- [ ] Documentation completed
- [ ] Final build ready

## 12.2 Update Log

| Days | Planned Goal | What Actually Happened | What Changed | Next Steps |
| ---- | ------------ | ---------------------- | ------------ | ---------- |
| Day 1 | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |
| Day 2 | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |
| Day 3 | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |
| Day 4 | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |

---

# 13. Risks and Unknowns

## 13.1 Risk Register

| Risk | Type | Likelihood | Impact | Mitigation Plan | Owner |
| ---- | ---- | ---------- | ------ | --------------- | ----- |
| `Ultrasonic sensor gives inaccurate readings at close range` | `Technical` | `Medium` | `High` | `Use IR sensors as emergency override for close-range detection` | `[]` |
| `Serial communication between Raspberry Pi and Arduino drops` | `Technical` | `Low` | `High` | `Add watchdog logic; Arduino defaults to stop if no command received` | `[]` |
| `Motor current draw causes Raspberry Pi to brown out` | `Technical` | `Medium` | `High` | `Use separate regulated power lines for motors and Raspberry Pi` | `[]` |

## 13.2 Biggest Unknown Right Now

**Response:**  
`[Write here]`

---

# 14. Testing

## 14.1 Technical Testing Plan

| What Needs Testing | How You Will Test It | Success Condition |
| ------------------ | -------------------- | ----------------- |
| `Ultrasonic sensor accuracy` | `Place objects at known distances and compare readings` | `Readings within ±1 cm of actual distance` |
| `IR sensor trigger` | `Move hand close to sensor and observe stop behavior` | `Motor stops immediately when IR detects obstacle` |
| `Touch sensor start/stop` | `Tap sensor and verify motor and LED response` | `System activates on first tap, deactivates on second` |
| `LED speed indicator` | `Vary obstacle distance and observe LED changes` | `Correct LED count lights up at each speed level` |
| `Multi-level speed control` | `Run car toward obstacle and log speed changes` | `Smooth deceleration across 4 levels` |

## 14.2 Testing and Debugging Log

| Date | Problem Found | Type | What You Tried | Result | Next Action |
| ---- | ------------- | ---- | -------------- | ------ | ----------- |
| `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |

## 14.3 Playtesting Notes

| Tester | What They Did | What Confused Them | What They Enjoyed | What You Will Change |
| ------ | ------------- | ------------------ | ----------------- | -------------------- |
| `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` | `[Write here]` |

---

# 15. Build Documentation

## 15.1 Fabrication Process (if any)

**Response:**  
`The fabrication process involved designing, manufacturing, assembling, and refining both the physical structure and electronic integration of the system.`

`Design (CAD Modeling): The initial model was created using CAD software, where components were designed based on the actual dimensions of the electronic parts. This ensured accurate fitting and minimized errors during assembly.`

`Cutting (Laser Cutting): The designed parts were fabricated using laser cutting techniques. Sheets were cut precisely according to the CAD model to create the structural base and mounts for components.`

`Assembly: Components were fixed using adhesives and mechanical supports. Certain parts were intentionally kept modular (not permanently fixed) to allow easy replacement and modification of electronics.`

`Surface Finishing: Some parts were sanded to smooth rough edges after cutting. Sawdust mixed with adhesive was used to fill gaps and uneven edges, improving structural finish. The final structure was then painted for better aesthetics and durability.`

`Revisions and Iterations: Multiple adjustments were made throughout the process, including refining alignment, improving structural stability, repositioning components, and optimizing sensor placement for effective detection.`

---

# 16. Build Photos

Add photos throughout the project.

Suggested images:

- early sketch,
- prototype,
- electronics testing,
- mechanism test,
- final build.

`[Upload images and link here]`

---

# 17. Final Outcome

## 17.1 Final Description

**Response:**  
`[Write here]`

## 17.2 What Works Well

`[Write here]`

## 17.3 What Still Needs Improvement

`[Write here]`

## 17.4 What Changed From the Original Plan

**Response:**  
`[Write here]`

---

# 18. Reflection

## 18.1 Team Reflection

**Response:**  
`[Write here — include what your team did well, what slowed you down, and how well you managed time, tasks, and responsibilities.]`

## 18.2 Technical Reflection

What did you learn about:

- electronics,
- coding,
- mechanisms,
- fabrication,
- integration?

**Response:**  
`[Write here]`

## 18.3 Design Reflection

What did you learn about:

- designing,
- delight,
- clarity,
- physical interaction,
- understanding,
- iteration?

**Response:**  
`[Write here]`

## 18.4 If You Had One More Hour

**Response:**  
`[Write here]`

---

# 19. Final Submission Checklist

Before submission, confirm that:

- [ ] Team details are complete
- [ ] Project description is complete
- [ ] Inspiration sources are included
- [ ] Sketches are added
- [ ] BOM is complete
- [ ] Purchase list is complete
- [ ] Budget summary is complete
- [ ] Mechanical planning is documented if applicable
- [ ] App planning is documented if applicable
- [ ] Code flowchart is added
- [ ] Task breakdown is complete
- [ ] Weekly logs are updated
- [ ] Risk register is complete
- [ ] Testing log is updated
- [ ] Playtesting notes are included
- [ ] Build photos are included
- [ ] Final reflection is written
