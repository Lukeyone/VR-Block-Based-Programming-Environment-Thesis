<div align="center">

# CubeCoder VR

### A VR block-based programming environment and controlled study of visual embellishments in learning

Build programs by physically grabbing, arranging and connecting code blocks in virtual reality, then execute them to guide a character through five progressively harder puzzle levels.

![Unity](https://img.shields.io/badge/Unity-2021.3.8f1-000000?logo=unity&logoColor=white)
![C%23](https://img.shields.io/badge/C%23-Programming-512BD4?logo=csharp&logoColor=white)
![OpenXR](https://img.shields.io/badge/XR-OpenXR%20%7C%20Oculus-5A45FF)
![Study](https://img.shields.io/badge/User%20Study-31%20Participants-0A7E8C)
![Thesis](https://img.shields.io/badge/Project-Honours%20Thesis-0057B8)

</div>

---

## Video demonstration

<div align="center">

<a href="https://www.youtube.com/watch?v=SXKN5MoZjaQ">
  <img src="https://img.youtube.com/vi/SXKN5MoZjaQ/hqdefault.jpg" width="720" alt="Watch the CubeCoder VR demonstration">
</a>

**[Watch the full demonstration on YouTube](https://www.youtube.com/watch?v=SXKN5MoZjaQ)**

</div>

![In-game demonstration of CubeCoder VR](docs/images/demo.gif)

## Project overview

CubeCoder VR was developed as the software artefact for my **Bachelor of Software Engineering (Honours)** thesis at the **University of Queensland**:

> **The Effect of Visual Embellishments in Virtual Reality on Learning**

The project combines two substantial pieces of work:

1. A custom VR visual-programming system in which users construct executable algorithms from physical 3D blocks.
2. A controlled user study comparing two versions of the game: one with celebratory and failure-related visual effects, and one without them.

Rather than typing source code, players create programs by placing colour-coded blocks into a spatial code tray and attaching condition or action blocks to compound structures. A custom runtime interprets the arrangement and translates it into visible character movement inside obstacle-based levels.

## Research questions

The thesis investigated:

1. **Do visual embellishments improve user experience in a VR educational game?**
2. **Do visual embellishments improve learning outcomes in a VR educational game?**

Visual embellishments were treated as responsive game effects rather than purely decorative scenery. The experimental version included effects such as:

- **Fireworks after successful level completion** to reinforce achievement.
- **Sequential bridge explosions after failure** to make an incorrect program visually consequential.

The control version retained the same core game, levels and educational content without these additional success/failure effects.

## User study

The completed study involved **31 university students**:

- **16 participants** used the version with visual embellishments.
- **15 participants** used the version without visual embellishments.

Each participant completed the following process:

```text
Consent and background information
              ↓
Seven-question programming pre-test
              ↓
VR controls demonstration and tutorial
              ↓
10–15 minute CubeCoder VR session
              ↓
Simulator Sickness Questionnaire (SSQ)
              ↓
Player Experience of Need Satisfaction (PENS)
              ↓
Seven-question programming post-test
```

The pre-test and post-test used the same seven programming questions, with a maximum score of **35 points**. The design measured learning change within participants as well as differences between the two experimental conditions.

## Study results

| Measure | With embellishments | Without embellishments | Statistical result |
|---|---:|---:|---|
| Mean PENS user-experience score | **5.80** | **5.54** | No significant difference, p = 0.3515 |
| Mean total simulator-sickness score | **592.74** | **731.73** | No significant difference, p = 0.3585 |
| Mean pre-test score | **18.13 / 35** | **19.33 / 35** | Baseline descriptive result |
| Mean post-test score | **22.66 / 35** | **20.57 / 35** | Descriptive result |
| Mean learning improvement | **+4.53 points** | **+1.23 points** | Weak evidence of a difference, p = 0.0947 |

### Interpretation

The study did **not** find a conventionally statistically significant difference in user experience or simulator sickness between conditions.

Participants exposed to visual embellishments improved by an average of **4.53 points**, compared with **1.23 points** in the control group. The between-group comparison produced **p = 0.0947**, which was treated as weak exploratory evidence—not proof—that visual embellishments may have supported learning.

The findings should be interpreted cautiously because of the small sample, variation in prior programming knowledge and the exploratory nature of the study. The primary contribution is the implementation and controlled evaluation of the idea, rather than a definitive claim that visual embellishments improve learning.

## Participant feedback

The open-ended responses provided concrete product-design findings.

### Common strengths

- The visual environments, art direction and sense of exploration were the most frequently praised elements.
- Participants liked seeing programming logic represented as physical objects that could be stacked and connected.
- The puzzle and problem-solving structure made introductory programming feel more engaging.
- Several participants described the experience as immersive, intuitive or particularly suitable for beginners.
- Multiple valid solutions to some levels supported experimentation rather than forcing one exact algorithm.

### Common pain points

- Motion sickness was the dominant usability issue, particularly during continuous locomotion and repeated turning to locate blocks.
- The reset and execute controls were placed too close together, causing accidental resets.
- Participants wanted to test, edit and rerun a program without losing the existing bridge or restarting the full sequence.
- Some block symbols, compound-block inputs and instructions were not sufficiently clear to beginners.
- Bugs, collision issues and frame-rate drops reduced comfort and occasionally confused the relationship between code and movement.

These findings informed the thesis recommendations: reduce physical turning, prefer teleportation or comfort locomotion, improve onboarding, enlarge and separate controls, and support iterative program testing.

## Five-level learning progression

| Level | Theme | Programming focus |
|---|---|---|
| **Tutorial Island** | Tropical beach and shipwreck | VR interaction, movement blocks and basic sequencing |
| **Conditional Cave** | Cavern and chasm | Conditional `if` logic and obstacle avoidance |
| **Crystal Conditions** | Narrow crystal passages | Combining world-state conditions with `if` and `while` blocks |
| **Function Fortress** | Ruined underground fortress | Defining and invoking reusable functions |
| **Algorithm Altar** | Ancient throne room | Final integrated puzzle using the concepts introduced across the game |

The environments were intentionally distinct so that each programming concept was associated with a memorable place and progressively harder challenge.

## What the user can program

| Concept | Implementation in CubeCoder VR |
|---|---|
| **Sequence** | Blocks execute in the order in which they are arranged in the code tray |
| **Movement** | Forward movement and directional/turning blocks control the level character |
| **Conditionals** | Conditional blocks query the current world state, such as whether movement is possible |
| **Loops** | While-style blocks repeatedly execute a connected action while a condition remains true |
| **Functions** | A separate function tray lets users define reusable behaviour and invoke it from the main program |

A program can resemble:

```text
Move Forward
While Can Move
    Move Forward
End While
Turn Right
Call Function
```

The program is assembled spatially, interpreted at runtime and translated into visible actions on the level map.

## Core software features

- **Physical code construction** — grab, move, connect, reorder and remove programming blocks using VR controllers
- **Spatial code tray** — arranges blocks into an executable sequence and highlights valid placement areas
- **Holographic input slots** — show where conditions and actions can be attached to compound blocks
- **Custom interpreter** — converts the physical block arrangement into runtime behaviour
- **Timed execution** — actions run sequentially through coroutines rather than completing simultaneously
- **Loop protection** — while blocks include a maximum-iteration guard to prevent unbounded execution
- **World-aware conditions** — condition blocks inspect the map state before selecting a branch or continuing a loop
- **Reusable functions** — users can build a secondary function sequence and call it from the main program
- **Puzzle progression** — levels include start tiles, goals, obstacles, limited block inventories and inter-level teleporters
- **Execution feedback** — messages, highlights and visual effects communicate program state and errors

## System architecture

```text
VR controllers
      ↓
XR grab and placement interactions
      ↓
Code blocks + input/output slots
      ↓
Code tray and function tray
      ↓
Structural checks and execution ordering
      ↓
Custom block interpreter
      ↓
Map and character controller
      ↓
Movement, collision checks and level feedback
```

### Block model

The execution system is organised around specialised block types:

- **Executable blocks** perform actions and expose an action-completion duration.
- **Conditional blocks** return a Boolean result based on the environment.
- **Compound blocks** accept connected condition/action blocks through spatial slots.
- **Function blocks** execute a reusable sequence stored in a separate tray.

For example, the movement condition accesses a central map tracker to determine whether the character can move. A while block repeatedly invokes its connected executable block, waits for the action to complete and stops when its condition becomes false or its iteration limit is reached.

### World and level layer

The programmed character operates on a level map containing:

- Walkable paths
- Obstacles and walls
- Start and goal tiles
- Direction indicators
- Level-transition teleporters
- Per-level block limits and instructional UI

This connects abstract control-flow concepts to immediately visible consequences in the environment.

## Technology stack

- **Unity 2021.3.8f1 (LTS)**
- **C#**
- **Unity XR Interaction Toolkit 2.3.2**
- **OpenXR Plugin 1.4.2**
- **Oculus XR Plugin 3.0.2**
- **TextMesh Pro**
- **Universal Render Pipeline / Shader Graph**
- Unity coroutines, physics, prefabs and scene-based level design

## Running the project

> **Repository size:** this is a complete Unity VR project containing scenes, models, textures, prefabs and other source assets, so the clone is large.

### Requirements

- Unity Hub
- **Unity 2021.3.8f1**
- An OpenXR-compatible VR headset and runtime
- A machine capable of running a Unity PCVR project
- Git installed locally

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/Lukeyone/VR-Block-Based-Programming-Environment-Thesis.git
   ```

2. Add the cloned directory as a project in Unity Hub.
3. Open it with **Unity 2021.3.8f1** and allow Unity to restore the packages.
4. Confirm that the appropriate XR provider is enabled under **Project Settings → XR Plug-in Management**.
5. Connect and start the headset runtime.
6. Open a gameplay scene from `Assets/Scenes/` — for example, `Alternate Level 1.unity` — and enter Play Mode.

XR configuration can vary between headsets and runtime versions. The project includes both OpenXR and Oculus XR packages, but local plug-in settings may still need to be adjusted for the target device.

## Repository structure

```text
├── Assets/
│   ├── Scenes/              # Gameplay and alternate experimental scenes
│   ├── Scripts/             # Block execution, map, interaction and UI logic
│   ├── Prefabs/             # Code blocks, character and reusable scene objects
│   ├── Materials/           # Block colours and environment materials
│   └── ...                  # Models, textures, audio and XR assets
├── Packages/
│   └── manifest.json        # Unity and XR package dependencies
├── ProjectSettings/         # Unity editor, rendering and XR configuration
├── docs/images/             # README demonstration media
├── .gitignore
└── README.md
```

## Engineering and research challenges

- Mapping a program's abstract syntax to physical, movable VR objects
- Preserving execution order while blocks are freely repositioned
- Designing input/output connections that remain understandable in 3D space
- Supporting control flow without a conventional text parser
- Synchronising code execution with visible character movement
- Preventing infinite loops in user-constructed programs
- Connecting conditional logic to live world state and collision information
- Building two comparable experimental versions while isolating the visual-effects variable
- Designing a short session that still exposed users to sequencing, conditions, loops and functions
- Collecting and analysing pre/post learning, user-experience and simulator-sickness data

## Limitations

- The study used a relatively small convenience sample of 31 participants.
- Prior programming, gaming and VR experience varied substantially between participants.
- Participants were not evenly balanced by prior coding ability across conditions.
- Only one practical level of visual-embellishment intensity was evaluated.
- Simulator sickness and locomotion discomfort affected some participants' ability to focus or complete levels.
- The project depends on an older Unity LTS and XR package configuration.
- The programming language intentionally supports a limited set of commands and control-flow structures.
- The repository is a research prototype rather than a production-ready educational platform.

## Potential future work

- Comfort locomotion and reduced physical turning
- Variables, values and additional data types
- Nested compound blocks and more advanced functions
- Non-destructive program testing, editing and replay
- Step-through execution, breakpoints and richer debugging tools
- Saving, loading and sharing programs
- Exporting visual programs to a conventional language
- Collaborative multi-user programming
- Accessibility improvements and alternative input methods
- A larger, better-balanced replication study with multiple effect intensities
- Updated OpenXR configuration and standalone-headset support

## Author

**Lachlan McDonald**  
Bachelor of Software Engineering (Honours), University of Queensland

[LinkedIn](https://www.linkedin.com/in/lachlanmcdonaldtech) · [GitHub](https://github.com/Lukeyone) · [Video demo](https://www.youtube.com/watch?v=SXKN5MoZjaQ)
